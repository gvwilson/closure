# Preserving Your Work

<p class="subtitle">saving what you can</p>

## If You Have Time

-   Preservation means making work usable by someone who was not part of creating it
-   Capture the *why*, not just the *what*:
    a README explaining the problem solved is more durable than API documentation
-   A "last known good state" document is worth more than an aspirational manual:
    what worked, what was broken, what was left undone
-   Archive to a persistent location, e.g., Zenodo or Software Heritage
    -   Be wary of institutional repositories:
	    you may lose access or (in event of a community or global threat) they may go away as well
-   Assign a [%g doi "DOI" %] to the final release so it can be cited
-   Mark deprecated versions in every relevant package registry,
    not just in the repository
-   Point to alternatives when deprecating:
    a migration guide matters more than a farewell post
-   Discussion archives (mailing lists, issue trackers) are often more valuable
    than formal documentation; export and preserve them before paid services lapse
-   Domain names lapse and get squatted; migrate content to free hosting before letting the domain go
-   Data preservation requires metadata: provenance, format, units, and known limitations
-   Follow [%g fair-principles "FAIR principles" %] (Findable, Accessible, Interoperable, Reusable) where possible
-   Dependencies rot: record exact versions and, if possible, a container image
    that reproduces the computational environment

<div class="callout" markdown="1">

Fifteen years ago,
a file-sharing system for scientific data based on the BitTorrent protocol
failed to find wide adoption because of the (quite reasonable) association in many institutions' collective minds
between BitTorrent and illegal downloading [%b Langille2010 %].
At the time of writing,
though,
many individuals and groups are turning to BitTorrent to share datasets that are at risk of disappearing
because of the protocol's resilience.

</div>

## If You Don't

-   Prioritize data over code
    -   Raw data is often irreplaceable
        while code in a version-controlled repository can be recovered or reconstructed
    -   If you can only do one thing, copy the data out first
-   One public copy beats zero private ones
    -   Push the repository to a public location immediately, even in its current messy state
    -   An imperfect archive that survives the loss of institutional infrastructure
        is better than a clean one that disappears with it
-   Export "everything else"
    -   issue tracker state, wiki pages, CI/CD configuration, deployment settings
-   Hand credentials to a trusted person outside the project before access is cut
    -   API keys and admin passwords stored in institutional systems
        will be unreachable once those systems are closed or your access is revoked
-   Write a one-paragraph finder's note at the root of the archive
    -   What this is, what state it was in when archived, what is missing, and a contact address
    -   This is not the same as the last known good state document above:
        it is narrower and faster to write,
        and is oriented toward someone who encounters the archive years later with no context

## Normalized Deviations

-   [%b Vaughan1996 %] showed that the Challenger disaster resulted not from a single catastrophic decision
    but from a long sequence of small ones in which warning signals were repeatedly noticed,
    reinterpreted as acceptable,
	and filed away until deviation had become the norm
-   Teams approaching closure often carry the same kind of backlog
-   Deliberate closure should therefore include an explicit audit of
    [%g normalization-of-deviance "normalized deviations" %]:
    things the team accepted because stopping to fix them felt too costly
-   A shutdown retrospective is most valuable when it names the things the team learned to live with,
    not only when it celebrates successes
-   Document these to record the project's actual state
    and to avoid passing silent assumptions to anyone who inherits the work

<section class="exercise" markdown="1">

## Exercises

### Write a Last Known Good State Document

Each participant drafts a one-page "last known good state" document for their own project
(or for Vaida's erosion data project if they prefer not to use their own):

1.  What does this project do, and what problem does it solve?
1.  What is currently working?
1.  What is broken or incomplete?
1.  Where does the data or code live, and how would someone get it?
1.  What are the most important things a successor would need to know?

Compare drafts in groups of three: what did others ask about that you had not thought to include?

## Normalized Deviations List

Work individually for ten minutes, then debrief in groups:

1.  Write down three things in your project that everyone on the team knows are wrong
    but that you have all learned to live with
	(e.g., a dependency nobody wants to touch
    or a process that only works because one person knows the trick).

1.  For each item, explain whether you would
    document it honestly in the last known good state document,
    fix it before shutdown,
    or leave it undocumented?

Which items were hardest to decide about?
What did you want to hide, and why?
What would a successor most need to know?

</section>
