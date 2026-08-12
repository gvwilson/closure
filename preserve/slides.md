---
title: Closing Time — Preserving Your Work
---

<section class="slide" markdown="1">
<div class="center">
<h1>Closing Time</h1>
<br>
<p>Preserving Your Work</p>
</div>
</section>

<section class="slide" markdown="1">

## If You Have Time

-   Preservation means making work usable by someone who wasn't part of creating it
-   Capture the *why*, not just the *what*:
    a README explaining the problem solved is more durable than API docs
-   A "last known good state" document: what worked, what was broken, what was left undone

</section>

<section class="slide" markdown="1">

## If You Have Time

-   Archive to a persistent location (Zenodo, Software Heritage)
    -   Be wary of institutional repositories — you may lose access
-   Assign a [%g doi "DOI" %] to the final release
-   Mark deprecated versions in every package registry
-   Point to alternatives: a migration guide matters more than a farewell post

</section>

<section class="slide" markdown="1">

## What to Preserve

-   Discussion archives (mailing lists, issue trackers) are often more valuable than formal docs
    -   Export and preserve before paid services lapse
-   Domain names lapse and get squatted; migrate content to free hosting first
-   Data preservation requires metadata: provenance, format, units, known limitations
-   Follow [%g fair-principles "FAIR principles" %] where possible
-   Dependencies rot: record exact versions and, ideally, a container image

</section>

<section class="slide" markdown="1">

## If You Don't Have Time

-   Prioritize data over code
    -   Raw data is often irreplaceable; code in version control can be recovered
    -   If you can only do one thing, copy the data out first
-   One public copy beats zero private ones
    -   Push the repository to a public location immediately, even messy

</section>

<section class="slide" markdown="1">

## If You Don't Have Time

-   Export everything: issue trackers, wikis, CI/CD config, deployment settings
-   Hand credentials to a trusted person outside the project before access is cut
-   Write a one-paragraph finder's note: what this is, state, what's missing, contact

</section>

<section class="slide" markdown="1">

## Normalized Deviations

-   [%b Vaughan1996 %]: the Challenger disaster resulted from a long sequence of small decisions
    in which warning signals were reinterpreted as acceptable until deviation became the norm
-   Teams approaching closure carry the same kind of backlog
-   Deliberate closure should include an explicit audit of
    [%g normalization-of-deviance "normalized deviations" %]:
    things the team accepted because stopping to fix them felt too costly
-   A shutdown retrospective is most valuable when it names
    the things the team learned to live with
-   Document these to avoid passing silent assumptions to anyone who inherits the work

</section>

<section class="slide" markdown="1">

### Downstream Impact

1.  Map your project's downstream dependencies.
2.  Categorize each dependent by impact severity:
    critical (their work stops),
    significant (their work is impaired),
    or minor (an inconvenience).
3.  Prioritize your list and draft a one-sentence message for each category.

</section>

<section class="slide" markdown="1">

### Write a Last Known Good State Document

1.  What does this project do, and what problem does it solve?
1.  What is currently working?
1.  What is broken or incomplete?
1.  Where does the data or code live, and how would someone get it?
1.  What are the most important things a successor would need to know?

</section>

<section class="slide" markdown="1">

## Normalized Deviations List

1.  Write down three things in your project that everyone on the team knows are wrong
    but that you have all learned to live with.
1.  For each, explain whether you would
    document it honestly in the last known good state document,
    fix it before shutdown,
    or leave it undocumented?

</section>
