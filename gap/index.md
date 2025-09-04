#  Governance, Assets, and Permissions

<p class="subtitle">start with the easy stuff</p>

-   Deliberate closure first: less traumatic, and the practices are good project hygiene anyway

## Governance

-   Every team needs explicit decision-making rules
    (e.g., [%g bdfl "BDFL" %] or [%g martha-rules "Martha's Rules" %])
-   Rules must include [%g suffrage "suffrage" %]: who can veto, not just who is consulted
-   Few projects have a `GOVERNANCE.md` file; fewer still include shutdown criteria
-   The [Apache Software Foundation][asf]'s [attic process][asf-attic] is a documented model:
    -   At least three active respondents required to keep a project viable

[%figure slug="gap-attic"
         img="apache-attic.svg"
         alt="Eight-step Apache Attic Process taken from https://attic.apache.org/process-howto.html"
         caption="Apache Attic Process"%]

-   Governance discussions forced under stress are far harder than those done in advance:
    cognitive load and interpersonal conflict make clear-headed decision-making much harder
-   In medicine, an advance directive specifies what care a patient wants
    if they become unable to speak for themselves
-   So write an [%g advance-directive "advance directive" %] for the project while it is still healthy [%b Towey2026 %]:
    -   Conditions for shutdown
	-   Who has authority to make the call
    -   What assets must be preserved
	-   What obligations must be honoured
-   A closure plan that sits in a drawer and has never been tested is a [%g fantasy-document "fantasy document" %]
    [%b Clarke1999 %]
    -   Organizations routinely produce plans that reassure regulators and funders
        but bear no relationship to what would actually happen under stress
    -   A `HANDOVER.md` written in an afternoon that no one outside the core team has read
    -   Ideally,
	    walk through the closure plan periodically
        to check that each step is actually executable with the people available
    -   But the word "ideally" is doing a lot of work in that sentence

## Coupling and Cascading Failure

-   Project infrastructure is often [%g tight-coupling "tightly coupled" %] in ways
    that only become visible during shutdown [%b Perrow1999 %]
    -   Failures in tightly-coupled systems are not aberrations
        but predictable outcomes of the system's design
-   [%b Singer2023 %] shows that organisations often invoke individual explanations
    to deflect systemic accountability
    -   "The driver wasn't paying attention" rather than "the dashboard was too complicated"
-   An account that pays for ten services,
    or a single personal login that controls a domain,
    means that an unexpected departure can cascade into complete loss of access
-   Handing over a GitHub organization and a domain name is not the same as
    handing over governance obligations or data privacy commitments
-   Treat any single point of control that cannot survive 48-hour unavailability as a bug
-   And treat every handover as an explicit asset transfer,
    not a transfer of "the project" as a whole [%b Marks2022 %]
    -   An asset transfer moves selected assets and obligations;
        the original legal entity persists or is wound down separately
    -   An entity transfer moves the entire legal entity including unknown liabilities
    -   Being explicit about what is and is not transferred
	    protects both the outgoing team and the incoming maintainers
-   As noted in the [introduction](@/intro/),
    there are legal obligations and restrictions around many of these
	-   Do *not* assume the law is comprehensible or sensible

## Permissions

-   Use dedicated organizational accounts rather than personal ones
    as soon as multiple people have privileged access
-   Keep a findable list of privileged actions and the accounts that can perform them
-   Use a [%g password-manager "password manager" %] for all organizational credentials

## Exercises

<section class="exercise" markdown="1">

## Project Inventory

1.  Work individually for ten minutes
    to make a list of everything that belongs to your project.

1.  Compare lists with otheres in your group.
    What did they include that you missed and vice versa?
	What did someone include that other people think isn't actually part of the project?

</section>

<section class="exercise" markdown="1">

### Assets and Obligations

Add one thing to each of the following lists:

-   Code, data, discussion archives, website, social media accounts,
    domain name, hardware, and…?
-   Hosting costs, software licenses, bank accounts, trademarks,
    partially-completed contracts, funding reports, confidential data obligations, and…?
-   Community goodwill, points of contact, and…?

</section>

<section class="exercise" markdown="1">

### Who and What

1.  What would your project be unable to do if you were unavailable for three months?

1.  Which of your project's activities depend on personal accounts
    rather than accounts dedicated to the project?

</section>

<section class="exercise" markdown="1">

### Write a Project Advance Directive

1.  Write a one-page document covering:
    -   The conditions under which this project should be wound down
        (not just "when funding runs out" but specific observable signals)
    -   Who has the authority to make that call
        (distinguish between who must be consulted and who has an actual veto)
    -   What assets must be preserved before shutdown is complete, and how
    -   What obligations must be honoured before the project can be considered closed

1.  Give your document to a partner and ask them to find one realistic scenario
    it does not handle.
    What happens if the person with authority is unavailable?
    What happens if two people with veto disagree?

Which conditions were hardest to write precisely?
Where did "who is consulted" blur into "who has a veto"?

</section>
