# Deliberate Closure

<p class="subtitle" markdown="1">when you have time to correct course</p>

-   Explore this first because it is less traumatic than the alternative
-   And because recommendations are things the project should be doing anyway
-   The most important assumption is that
    *you have time to make changes to the project as part of shutting it down*

## Governance

-   People often conflate teams with projects
    -   But team may disband when the project completes, or take on another project
    -   And membership of team may change during project
-   Every team should have explicit rules for making decisions
    -   E.g., [BDFL](g:bdfl) or [Martha's Rules](g:marthas-rules)
-   Every team also needs explicit rules for deciding [suffrage](g:suffrage)
    -   "Being consulted" is meaningless without further stipulation
    -   "Who must agree in order for this to happen?"
    -   "Who can veto proposals?"
-   Growing number of open source projects have a `GOVERNANCE.md` file in their repository
    -   But very few of these include explicit shutdown criteria
-   Put this in place *before* discussion of endings
    -   It's hard enough to decide under normal circumstances
    -   Harder still when also thinking about shutdown
-   Example: the [Apache Software Foundation][asf] (ASF)
    -   Board can request a roll call
    -   At least three people must respond to a "do a release" email for the project to be considered viable

<section class="exercise" markdown="1">

### Exercise

1.  Who is currently a member of your project?
    How do you know?
    How do they (and others) know?
    What does being a member actually mean?

2.  How does someone stop being a member, either voluntarily or otherwise?

</section>

## Assets and Obligations

-   You can't manage things you aren't aware of
-   Every project has [assets](g:asset) that have some sort of value to someone
    -   Source code in a repository
    -   Discussion archives that explain decision making (especially valuable to genAI)
    -   A website and/or social media accounts
    -   Software licenses
    -   Hardware
    -   Name recognition (possibly even a trademark)
    -   Community goodwill
    -   [Collective understanding](g:collective-understanding) [[](b:Baetjer1997)]
-   Project may also have [obligations](g:obligation)
    -   Hosting charges
    -   Software licenses
    -   A bank account
    -   Partially-completed research contracts or upcoming software releases
    -   Reports to funding agencies
    -   Security of confidential data
-   You may have legal responsibilities around both
    -   E.g., institution may require you to return lab equipment
    -   Or require you to make best effort to realize full commercial value
    -   *Ask someone*
-   You must also think about self-defence
    -   Having a gambling company take over your domain is unpleasant

<section class="exercise" markdown="1">

### Exercise

1.  Make a list of the things that belong to your project.
    Compare it with the lists made by other project members:
    what did they include that you didn't and vice versa?

2.  Imagine your project was going to shut down in three months.
    What would you have to deliver, to whom, in that time?

</section>

## Permissions

-   Permissions are the overlap of governance with assets and obligations
    -   Who can do what, with what
-   Easiest to use personal accounts for everything
    -   Particularly in a project's early days when you're not sure it's going anywhere
-   As soon as multiple people can do things that outsiders cannot,
    use dedicated accounts rather than personal ones
    -   Enables continuity if (when) people move or are unavailable
-   And *make a list* of what those special actions are
    -   Keep it somewhere findable (e.g., `CONTRIBUTING.md` in a project repository)
-   Use a [password manager](g:password-manager) for all organizational accounts
    -   Actually, use one for your own work as well [[](b:Small2021)]

<section class="exercise" markdown="1">

### Exercise

1.  What is your project not able to do if you are unavailable for an extended period?
    (For example, "cannot revise a paper" or "cannot publish a new version of a package".)

2.  Which of your project's activities are associated with personal accounts (yours or others)
    rather than accounts dedicated to the project?

</section>

## Community

-   You may want to stay in touch with some or all of the team after the project ends
    -   "May" and "some" because not every project ends happily
    -   Even if it doesn't, it's useful to maintain good relations with funders, reviewers, customers, etc.
-   Shutdown is often contentious:
    people who have complained but never contributed may criticize you
    -   Can help to phrase shutdown notice as "putting into hibernation"
-   Take inspiration from the ASF's procedure
    -   Don't start by announcing shutdown
    -   Instead, announce that you (singular or plural) are going to stop work
        and ask for volunteers to take over

<div class="callout" markdown="1">

Do *not* accept people you don't already know as successors on your project:
there is a small but growing risk that they will try to use it
for [supply chain attacks](g:supply-chain-attack),
or repurpose your site to advertise gambling, porn, or extremist politics.

</div>

-   If you are not going to keep the project's domain,
    move the content to a free hosting service (e.g., GitHub Pages)
    and put redirects in place
-   Make sure vendors, donors, and others with a legally binding stake in the project
    have a way to contact you and/or the team after the project's email addresses are shut off
-   Tell your team and your community as much as you can as soon as you can
    -   Knowing that a project is shutting down will inevitably affect morale
    -   Don't add uncertainty or rumors to the mix
-   Things to tell them:
    -   Reasons (as much as you can)
    -   Timelines (and updates to timelines, because these always shift)
    -   What's happening to assets and obligations

## What You Can Skip

-   The introduction explained that "document everything" doesn't work in practice because:
    -   People are always too busy to keep the documentation up to date
    -   It's hard to know which bits are actually going to be useful in the future
        (but experience teaches that most aren't)
-   Force yourself to make an exception for governance, assets & obligations, and permissions
    -   The project will grind to a halt without these
    -   And there may be legal or reputational risks to not doing it
-   But if you're shutting the project down, it's OK not to put effort into:
    -   User-oriented documentation (e.g., tutorials)
    -   Project dependencies
    -   More tests or examples

## Hold a Wake

-   If you have time, it's worth doing a team retrospective
    -   What did we do well?
    -   What could we have done differently?
    -   What did we learn along the way?
    -   What are we going to remember?
-   The last of these may be the most important
    -   Endings are sad, but they can be sweetened

<div class="callout" markdown="1">

[Mike Hoye suggested][hoye-retire] that
we should retire the account names of Unix greats
in the way that sports teams retire jersey numbers,
and for the same reasons.
End-of-project t-shirts or laptop stickers
are another great way to say,
"We were here and we did something good,"
and so is getting the whole team on a call
to watch as you push the "archive" button on your repository.

</div>
