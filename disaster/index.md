# Disasters for Small Teams

In 2025, the US government launched an unprecedented series of
short-notice cuts and shutdowns at its own scientific research groups.
Twelve months later, GitHub briefly dropped below 90% availability for
the first time, and at the time of writing, wildfires in France, Spain,
and elsewhere have forced researchers from the homes and labs. These
events and others have reminded us just how dependent we have become on
computing to do science, and just how fragile our computing systems can
be.

This paper is a short guide to disaster planning and recovery for a
research software team whose "IT department" fits around a single table.
The recommendations assume you are doing everything yourself on top of
your regular job, that you *aren't* an experienced system administrator,
and that a single person's absence can leave a critical gap.

## Tip 1: Know your risks.

For a small team, the most likely disasters are a stolen or dead laptop,
a team member who takes the only knowledge of something with them, an
online service provider that locks you out or disappears (including
another research project that loses its funding), or a mistaken
`DROP TABLE` or `rm -rf` that wipes something important. Plan for these
specifically before worrying about floods or fires.

Start by making a point-form list of every service your team depends on
to function, such as source code hosting, email, chat, your own
database, the external data repository you share data with, the web
service you provide to colleagues, the web services they provide that
you use, your grant-management portal, your domain registrar, your cloud
provider, the laptops your team work on, and any shared lab instrument
controllers. For a small team, this will take about an hour the first
time through, and 15-30 minutes per quarter for review and upate.

A Markdown file in your source control repository or a shared Google Doc
is the right tool for this. For each service, answer two questions in
that document:

1.  How long can you be without it before work stops dead? This is your
    *Recovery Time Objective* (RTO).

2.  How much data can you afford to lose: the last hour's work, the last
    day's, a week's? This is your *Recovery Point Objective* (RPO).

Next, identify the single points of failure that are within your
control. Common ones in a small team are the person who knows the
deployment process, the credit card that pays for all the cloud
services, and the SSH key that can access production. For each one, ask
what happens if it disappears. For example, if your cloud provider
suspends your account by mistake, can you still run analysis pipelines?
Or if your domain registrar is compromised, how quickly can you point
DNS somewhere else?

## Tip 2: Make a plan.

Once you have an idea of risks and impact, write a plan in a single
shared document that everyone on the team can find in thirty seconds or
less. Remember that if the plan lives only on Dropbox and Dropbox is
down, you effectively have no plan. You should therefore store the plan
in at least two places that cannot fail simultaneously, such as the
shared team drive *plus* a printed copy in a desk drawer or a PDF saved
on your phone (or better yet, every team member's phone). Pin the link
to the document in your team chat, and if you have a physical office,
tape a printed copy to the fridge.

State the disaster declaration criteria in plain language, such as "our
data repository has been offline for more than a day" or "we have found
ransomware encryption on a shared drive". At this scale, every team
member is part of the recovery team, so make sure everyone has read the
plan, understands the criteria, and knows their first action if a
disaster is declared.

Your plan should consist of a checklist for each scenario, written as a
numbered series of specific actions like this:

1.  Send a message to `#incidents` in Slack.

2.  SSH into the database host.

3.  Run `./restore-db.sh prod latest`.

4.  Verify the database now returns an HTTP 200 status code.

> If a step requires a command that only one person knows, you have a
> *lottery-factor* problem. At this point you should therefore ask
> yourself, "If Alice wins the lottery and moves to Bali tomorrow, can the
> rest of the team keep things running?" This is the hardest part of
> planning by far, because Alice probably doesn't recognize all the things
> she does that no one else knows how to do, and no one else does either
> because they are not doing them.

## Tip 3: Back up everything.

Follow the *3-2-1 rule* [%b Krogh2009 %]: three copies of every critical
dataset, on two different types of media, with one copy off-site. For a
small team these three copies are usually (a) the live production
database, (b) an automated nightly backup to the cloud, and (c) a weekly
download to a drive stored in someone's home (*not* the office).

Automate backups by writing a shell script that runs nightly, names the
backup file with the date and time, and uploads it to the cloud. Use
`cron` or systemd timers to schedule it. Automation is crucial: if you
have to remember to run the script, it will not get run. The small-team
tool is as simple as `pg_dump` plus `aws s3 sync`: nothing more
expensive or complicated is needed.

Back up your source code to at least two different services (*not* two
different repositories on the same service). GitHub is becoming less and
less reliable, and every service is subject to account bans or billing
failures. As we learned from the demise of SourceForge [%b Tamburri2020 %],
a `git push --mirror` to a secondary remote may be the most
cost-effective one-liner you ever write.

Back up your configuration as well, such as DNS records, environment
variables, and CI/CD pipeline definitions. These are small in size but
catastrophic to reconstruct from memory (and no, AI cannot presently do
it for you). A single export once a week, stored alongside your code
backups, is sufficient.

Finally, *test a full restore from backup* at least once a year.
Anecdotally, about a third of backups fail to restore completely.
Remember that you may need to restore several times in a real disaster.
A recovery script that corrupts data the second time it is run is
therefore as bad as no script at all. Check that your automation is
*idempotent* by running it and then running it again.

> More advanced teams should consider using managed databases with
> automated daily snapshots and point-in-time recovery enabled. They cost
> more than running your own PostgreSQL on an EC2 instance, but they are
> also more likely to still be running when you wake up in the morning. On
> the other hand, they make you dependent on yet another cloud service. If
> you can put backup storage on a separate cloud account with credentials
> that are not stored on any production server, do so. If an attacker
> compromises your application server, they should not get your backups as
> well.

## Tip 4: Communicate clearly.

Choose a single communication channel that does not depend on your
normal infrastructure. For example, if you use Slack, agree *in advance*
on a Signal group or plain old phone tree that you will use if Slack
goes down. Make sure the fallback is written in your plan.

Keep a printed (or phone-screenshot) contact list with every team
member's mobile number and a personal email address. As with the plan
itself, do not store this only in a shared drive that may be affected by
an outage.

Copying and pasting is faster than composing under stress, so pre-write
three messages and store them with the plan and in your password
manager's shared vault:

1.  For the team: "This is a declared incident: meet in the Signal
    group."

2.  For users or stakeholders: "We are investigating an outage and will
    update you within 60 minutes."

3.  For afterward: "Service is restored: this is what happened and what
    we are doing to prevent recurrence."

If you have customers, users, or a PI who needs to know what is going
on, designate one person as the communicator so that everyone else can
focus on fixing the problem. The communicator does not need to be
technical: they need to be calm and reliable. Remember that silence
erodes trust faster than bad news, so update stakeholders at regular
intervals (for example, every 60 minutes or at 10:00 am and 3:00 pm)
even if the update is "still working on it."

## Tip 5: Test the plan.

The most revealing test for a small team is to hand the recovery
checklist to the newest team member, create a sandboxed environment for
them to make mistakes in, and ask them to execute the plan without help.
Every point where they get stuck is a documentation or automation gap.

If no one has joined your team recently, the second-best way to test
your plan is an hour-long walkthrough. Gather the team and present a
scenario, such as, "It's Tuesday morning and all of Monday's data has
disappeared from the database. What do we do?" Try to pick the thing
that scares you most. For example, if you have never actually restored
the database from a backup, do that. Walk through the checklist step by
step and fix anything that is missing, wrong, or stale then and there.
Only test one thing a quarter: your team has other things to do, and you
don't want them to file this under "chore to avoid".

Keep track of how long tests take and compare against your RTO. If
restoring the database takes four hours but your RTO is two hours, you
must either fix the former or adjust the latter.

## Tip 6: Watch for trouble.

Monitor the things that you would get out of bed at 3:00 a.m. to fix.
Free-tier monitoring services like [Uptime Robot](https://uptimerobot.com/)
and [Healthchecks.io](https://healthchecks.io/) are infinitely better
than no monitoring. Do not roll your own, at least not to start with.

Check your cloud bill at least once a month: a misconfigured resource
can generate a catastrophic bill even for a small team. If you can, set
budget alerts in your cloud provider's console at 50% and 90% of your
normal monthly spend, sent to at least two people. Most cloud providers
offer free-tier budget alerting adequate for a small team.

## Tip 7: Lock down your accounts.

Enable multi-factor authentication (MFA) on every account: this is the
highest-impact security measure you can take [%b Smalls2021 %]. SMS-based
MFA is better than no MFA, but an authenticator app or passkey is better
than SMS.

Use a password manager like 1Password or Bitwarden for the whole team.
Bitwarden's free tier is often enough for a 3--5 person team. Every
shared credential goes in the password manager: no one shares passwords
over chat or email. Print the password manager's recovery code and store
it somewhere physically safe, because if you lose access to the password
manager you lose access to everything.

Register your domain with a registrar that supports two-factor
authentication and lock your domain against transfers. Enable
auto-renewal on every domain and every TLS certificate. Set a calendar
reminder to check that auto-renewal is still working once a quarter.
Make sure at least two people have critical administrative credentials,
such as the cloud root account, the domain registrar login, and the
payment method for infrastructure, and make sure these credentials are
not tied to a single phone number or email address.

Finally, maintain an offboarding checklist, and when someone leaves,
revoke their access as soon as you can. The offboarding checklist is a
form of disaster prevention: a disgruntled former team member with
lingering access is trouble you don't need.

## Tip 8: Harden your systems.

Make a simple, explicit policy about where data lives, such as "patient
data is never copied to a personal laptop," or "database dumps are
encrypted at rest." If your policy will not fit comfortably on a single
page in an 11-point font, rewrite it until it does.

> If you are handling sensitive data, check whether your institution has a
> security office that offers free consultation. You may have obligations
> you are not aware of under HIPAA, GDPR, or your funder's data-management
> plan.

Keep your laptops and servers patched. Enable automatic updates for
operating systems, browsers, and any server-side package manager. The
inconvenience of an unexpected reboot is less than the inconvenience of
ransomware.

For on-premises equipment like a lab server or a NAS, buy a cheap UPS
and configure it to trigger a clean shutdown when the battery reaches
20%. Replace the UPS battery every three years: they have a tendency to
degrade silently.

Prepare a short, written response for ransomware. If someone on the team
sees a ransom note on a shared drive, their first action is to
physically disconnect the affected machine from the network and then
call the designated incident lead. Do not try to negotiate or pay
without consulting legal counsel: most jurisdictions have regulations
about ransomware payments.

## Tip 9: Stabilize, then investigate.

The most important rule of incident response is, "Stabilize first,
investigate later." Your first goal when something breaks is to contain
the damage, not to find the root cause.

Assign clear roles for the duration of the incident: one person leads
the technical response, one person handles communication using the
pre-written messages from Tip 4, and everyone else does what the leads
tell them to.

Create an incident log *as you work*: a shared Google Doc or a thread in
your out-of-band Signal group is good enough. Timestamp every
significant action, such as "14:32: noticed database unreachable" and
"14:35: attempted restart." The log keeps the team in sync and gives you
a record for the post-incident review.

Escalate early. If you are on a cloud provider's support plan, open a
ticket the moment you suspect the problem is on their side. You can
close it if you fix things yourself; you cannot get back the two hours
you spent hoping something outside your control would resolve itself.

Finally, treat every incident as a disaster-recovery test, and conduct a
short review within 48 hours of the incident. The goal is to identify
what in the system allowed the incident to happen, not who made a
mistake. Write down one concrete action item and assign it to one person
with a deadline. If you cannot find an outside moderator for the review,
have the team member *least* involved in the incident lead it.

## Tip 10: Count the cost.

You probably don't have a budget line item for disaster recovery, but
you still have costs. Identify them: the extra cloud spend for backup
storage, the cost of a password manager, the domain and certificate
renewals, and perhaps a small monthly fee for an off-site backup
service. Calculate what a day of downtime costs you in concrete terms,
such as lost sales, missed experiment time, or a blown grant deadline.
For a grant-funded research software team, "cost" also includes lost
experiment time, missed paper deadlines, and collaborators who stop
trusting you. That number tells you whether it is worth spending
$50/month on a managed database or $200/year on a backup service.
