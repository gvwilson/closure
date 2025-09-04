# Introduction

<p class="subtitle" markdown="1">setting the scene</p>

-   For every beginning there must be an ending
-   But we don't like to talk about that
    -   Thousands of books in print about how to start a business
    -   Only a handful about how to pass one on or wind one down
    -   And many of those are really about how to sell out at the right time
    -   Because mortality scares us
-   Preparing for the end can make it less painful
    -   And less likely:
	    if we think about how things might end, we might be able to prevent some endings
    -   It also helps make what happens before then more enjoyable

## Two Kinds of Ending

-   [%g deliberate-closure "Deliberate closure" %]
    -   You made the decision yourself
    -   Or have enough advance notice to make plans
    -   You can learn as you go and make changes along the way
-   [%g abrupt-closure "Abrupt closure" %]
    -   Short notice, and usually not your decision
    -   You only get one shot at it and aren't able to make changes as you go along
-   We want the former, but often have to deal with the latter
-   [%b Wilson2014 %] outlined how [%g rse "research software engineers" %]
    should organize their projetcs
-   [%b Wilson2017 %] was in part a rebuttal
    -   Most people don't have time to do everything the "right" way
    -   By which we usually mean "their employers don't give them enough time"
    -   So comparing what they do to "best practices" is as unfair as
        comparing what a surgeon does at leisure in a well-equipped hospital
        to what a paramedic does at a crash site
-   This workshop addresses both cases
    -   Vaida has time to plan
        and to correct things that she initially gets wrong
    -   Liam only has time to do a few things,
        and will not be able to go back and fix anything he doesn't get right

<div class="callout" markdown="1">

An [%g abstinence-solution "abstinence solution" %] is one that requires people
to do things we know they actually won't
(See also "[%g bullshit "bullshit" %]" [%b Frankfurt2005 %].)
In particular, "document everything" doesn't work:
people will always short-change writing descriptions of work in favor of actually doing work
and fail to write down the parts of their work that they think are obvious
in part because most of what we can write today doesn't actually address tomorrow's actual needs.

</div>

## The Survival Arc

-   [%b Ripley2008 %] synthesised research on how people behave when disaster strikes
    and identified a three-stage [%g survival-arc "survival arc" %]:
    -   Denial: refusal to believe that the situation is as serious as evidence suggests
    -   Deliberation: a period of paralysed uncertainty about what to do
    -   Decision: action, which may or may not be correct
-   The denial phase usually consumes far more time than people expect
    -   Thinking through the scenario before it happens dramatically shortens it
-   The period between a credible sign that a project is in trouble
    and the first concrete closure action will be longer than planners assume,
    particularly under abrupt conditions
    -   Rehearsal converts a novel emergency into a recognized pattern and shortens denial
-   Business owners who were satisfied with their exits had started planning years in advance
    [%b Burlingham2014 %]
    -   The most common mistake is skipping early stages because they feel premature

## What We Can Hope For

-   The [%g sunk-cost-fallacy "sunk cost fallacy" %] keeps projects alive past their useful life
-   [%b Weitzel1989 %] describes a five-stage model of organisational decline:
    -   Blindness: warning signs go unrecognised
    -   Inaction: signs are seen but nothing changes
    -   Faulty action: the wrong remedies are tried
    -   Crisis: resources are depleted and options close off
    -   Dissolution
-   The moment when shutdown becomes undeniable is rarely the moment it became inevitable:
    the warning signs were there earlier [%b Whetten1980 %]
    -   Recognizing which stage a project is in determines which interventions are still available

<div class="callout" markdown="1">

[%b Palazzo2025 %] identified patterns in the dynamics of corporate scandals.
Recognizing them early can give people warning that projects are going to fail.

<div class="center">
<table>
  <tr>
    <td style="border: none; padding-right: 2rem;">
      rigid ideology
      <br>
      toxic leadership
      <br>
      manipulative language
    </td>
    <td style="border: none; padding-right: 2rem;">
      corrupting goals
      <br>
      destructive incentives
      <br>
      ambiguous rules
    </td>
    <td style="border: none; padding-right: 2rem;">
      perceived unfairness
      <br>
      dangerous groups
      <br>
      slippery slope
    </td>
</table>

</div>

## Threat Models

-   What situation you are in usually depends on external factors
    -   Use the technique of [%g threat-modeling "threat modeling" %] from computer security
        to think about them
-   [%g individual-threat "Individual threats" %] affect one or a few members of your team
    -   Can come from mundane career or life changes (illness, new job opportunity)
    -   Or external factors (international students' visas revoked with little warning)
    -   [%g leadership-threat "Leadership threats" %] are specifically aimed the project's leader
        (e.g., being targeted in the media for politically unpopular research findings)
-   [%g community-threat "Community threats" %] affect large groups
    -   E.g., department being shut down
    -   Affect so many people at the same time that the community cannot buffer the shock
        -   And might not survive it
    -   [Climategate][climategate] affected dozens of people directly
        and damaged the entire climate research community
-   [%g global-threat "Global threats" %] affect everyone
    -   Which means other communities cannot help
    -   And there may not be anywhere to run to
    -   E.g., current attacks on science in the United States

<div class="callout" markdown="1">

Governments make emergency plans to deal with community threats
(if they are responsible enough to admit those threats exist).
When governments themselves are in upheaval,
people turn to [%g civil-society "civil society" %] for help [%b Solnit2010 %].

</div>

## Stay Within the Law

-   Ensuring your work remains usable is not worth putting yourself at legal risk
    -   Institutions, journals, and funders have policies for licensing and sharing [%b Katz2018 %].
    -   So find out what those rules are and make sure you stay within them
	-   Which isn't necessarily the same thing as saying "follow them" [%b OSS1944 %]
-   If you don't know if there is a policy or not, *ask someone*
    -   Look for an [Open Source Program Office][ospo] (OSPO) or intellectual property (IP) office
-   Here and elsewhere, use email rather than chat or video calls
    so that you have a record of everything said by both parties
    -   Your memory isn't perfect (particularly under difficult circumstances)
    -   And unfortunately, people may change their minds about what they said, meant, or promised

<div class="callout" markdown="1">

There is often a difference in large bureaucratic organization
between the rules as written and the rules as enforced.
If you are leaving your position on short notice or under difficult circumstances,
you may want to be selective about which forms you fill in proactively
and which you "just haven't gotten around to yet".
Members of marginalized groups have had more practice with these tactics
than members of privileged groups [%b Scott1987 %];
if you belong to the latter,
a conversation or two with selected colleagues may help you see your priorities more clearly.

</div>

## Not Covered

-   Community building
    -   Lots of good guides [%b Alinsky1989 Brown2007 Lakey2018 %]
    -   We assume you have to use the community you already have
-   Communication skills
    -   We'll talk about *what* to say but not (much) about *how* to say it
    -   See [%b Kuchner2011 %] for some useful insights
-   For-profit businesses
    -   We assume your project isn't supposed to turn a profit
    -   And that growth for its own sake hasn't been your goal [%b Burlingham2016 %]

## Exercises

<section class="exercise" markdown="1">

### Quick Check

1.  Are you handing over or shutting down?
    -   Can think of shutdown as "succession to zero"
1.  Do you have days or months to prepare?
    -   The former is usually involuntary
    -   The latter allows for (some) structural changes before and during handover
1.  Can you act unilaterally or do other people have a veto?
    -   *Not* "have a stake in the outcome", but rather can disagree with you and make it stick
    -   Are those "other people" your peers or your superiors (e.g., your employer)?
1.  Can you talk to someone who has been through this before?

</section>
