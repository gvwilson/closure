---
title: Closing Time — Governance, Assets, and Permissions
---

<section class="slide" markdown="1">
<div class="center">
<h1>Closing Time</h1>
<br>
<p>Governance, Assets, and Permissions</p>
</div>
</section>

<section class="slide" markdown="1">

## Why Start Here

-   Deliberate closure is less traumatic than emergency shutdown
-   The practices discussed here are good project hygiene regardless
-   Use software-intensive projects for examples

</section>

<section class="slide" markdown="1">

## Governance

-   Every team needs explicit decision-making rules
    -   [%g bdfl "BDFL" %] or [%g martha-rules "Martha's Rules" %]
-   Rules must include [%g suffrage "suffrage" %]: who can veto, not just who is consulted
-   Few projects have a `GOVERNANCE.md`; fewer still include shutdown criteria
-   The [Apache Software Foundation][asf]'s [attic process][asf-attic] is a documented model
    -   At least three active respondents required to keep a project viable

</section>

<section class="slide" markdown="1">

## The Advance Directive

-   Governance discussions forced under stress are far harder
-   In medicine, an advance directive specifies what care a patient wants
    if they become unable to speak for themselves
-   Write an [%g advance-directive "advance directive" %] for the project while it is healthy [%b Towey2026 %]:
    -   Conditions for shutdown
    -   Who has authority to make the call
    -   What assets must be preserved
    -   What obligations must be honoured

</section>

<section class="slide" markdown="1">

## Fantasy Documents

-   A closure plan that has never been tested is a [%g fantasy-document "fantasy document" %] [%b Clarke1999 %]
    -   Organizations produce plans that reassure regulators
        but bear no relationship to what would actually happen
-   A `HANDOVER.md` written in an afternoon that no one outside the core team has read
-   Ideally, walk through the closure plan periodically
    -   But the word "ideally" is doing a lot of work in that sentence

</section>

<section class="slide" markdown="1">

## Coupling and Cascading Failure

-   Project infrastructure is often [%g tight-coupling "tightly coupled" %] [%b Perrow1999 %]
    -   Failures are predictable outcomes of the system's design
-   [%b Singer2023 %]: organisations invoke individual explanations to deflect systemic accountability
-   One account paying for ten services means one departure can cascade into total loss
-   Handing over a GitHub organization is not the same as handing over governance obligations
-   Treat any single point of control that can't survive 48-hour unavailability as a bug

</section>

<section class="slide" markdown="1">

## Asset Transfer vs. Entity Transfer

-   Treat every handover as an explicit [%g asset-transfer "asset transfer" %] [%b Marks2022 %]
    -   An asset transfer moves selected assets and obligations;
        the original legal entity persists
    -   An entity transfer moves the entire legal entity including unknown liabilities
    -   Being explicit protects both the outgoing team and the incoming maintainers
-   There are legal obligations and restrictions around all of this
    -   Do *not* assume the law is comprehensible or sensible

</section>

<section class="slide" markdown="1">

## Permissions

-   Use dedicated organizational accounts rather than personal ones
    as soon as multiple people have privileged access
-   Keep a findable list of privileged actions and the accounts that can perform them
-   Use a [%g password-manager "password manager" %] for all organizational credentials

</section>
