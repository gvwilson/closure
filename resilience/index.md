# Resilience

<p class="subtitle">what you can do right now</p>

In 2013,
the government of Canada ordered the closure of
five of the Department of Fisheries and Oceans' seven libraries [[](b:Nikiforuk2013)].
No one knows how many thousands of volumes of irreplaceable environmental records were destroyed,
but even scientists who were directly affected did not make plans in case something similar happened again.
In contrast,
when faced with the prospect of a populist demagogue becoming president,
researchers in Argentina knew from their collective experience what might happen next
and took action accordingly.

And then Donald Trump was re-elected
and an unprecedented assault on American science began.
Except it wasn't really unprecedented:
from anti-vax hysteria to climate change denialism
to banning the teaching of evolution in schools,
reactionaries have been attacking science and scientists for decades.
We hadn't prepared,
even though their manifesto warned us what was coming.

## Licensing

Making code and data publicly available does not ensure that other people can use it;
you maintain all copyright unless you explicitly include a license,
so they may still need explicit permission
or may simply be unsure whether they do or not.
The Open Source Initiative (OSI)
maintains a list of \href{https://opensource.org/licenses}{open source licenses} it has approved;
the implications of these licenses are widely understood,
so choosing one of those will make your project more understandable to others.
Please do \emph{not} try to write your own license
or simply waive copyright and place the software into the public domain,
as what is meant by ``public domain'' varies from country to country.
(In countries such as France and Germany
it may not actually be possible to waive copyright and place a work in the public domain.)

More broadly,
\href{https://creativecommons.org/}{Creative Commons} licenses can be used for documentation or research reports
but should be avoided for actual code,
while \href{https://ethicalsource.dev/}{ethical licenses}
or licenses based on the \href{https://blueoakcouncil.org/license/1.0.0}{Blue Oak Model License} may also be appropriate.
\href{http://choosealicense.com}{choosealicense.com} and other sources provide guidance \cite{Fogel2020,Fortunato2021};

Whatever license you choose,
place its text in a file called \texttt{LICENSE}, \texttt{LICENSE.txt}, or \texttt{LICENSE.md}
in the root directory of your project,
as this is where people and automated tools alike will look for it.

\begin{quote}
  \noindent
  \textbf{The law, again}

  Most discussion of open source licensing focuses on circumstances in a handful of affluent countries
  in the same way as discussion of fiscal sponsorship (Tip~3).
  For example,
  many Latin American countries have access to information laws that include research outcomes and artifacts.
  You can publish data and software under that,
  but the institution sets the license type,
  and you must use institutional repositories.
  As always,
  consult \emph{local} legal experts before taking action.
\end{quote}

## Hosting

the threats to your project are political as well as technological (Tip~2),
so you should ensure that loss of institutional support
(or worse, that institution turning on you)
does not mean loss of access.

\begin{quote}
  \noindent
  \textbf{The road not taken}

  Fifteen years ago,
  a file-sharing system for scientific data based on the BitTorrent protocol
  failed to find wide adoption because of the (quite reasonable) association in many institutions' collective minds
  between BitTorrent and illegal downloading \cite{Langille2010}.
  At the time of writing,
  though,
  many individuals and groups are turning to BitTorrent to share datasets that are at risk of disappearing
  because of the protocol's resilience.
\end{quote}

\href{https://github.com/}{GitHub},
\href{https://gitlab.com/}{GitLab},
and \href{https://bitbucket.org/}{BitBucket}
are social coding platforms centered around Git,
a widely-used open source version control tool.
However,
they are all commercial entities based in the same legal jurisdiction,
which means they are vulnerable to \emph{correlated threats}:
trouble with any of them may mean trouble with all of them.
\href{https://codeberg.org/}{Codeberg},
while currently much smaller,
is a non-profit based in a different jurisdiction;
consider mirroring your work there or using it as your primary host.
Keep in mind that persistent code archival is not a feature of development platforms.
Repositories can be altered,
made private,
or deleted
(also as a result of government takedowns\footnote{\url{https://github.com/github/transparency/tree/main/data/government_takedowns}});
the platform itself may be shut down
(as happened to the non-profit Gna!\footnote{\url{https://en.wikipedia.org/wiki/Gna!}}),
or it may change its revenue model
(as happened with SourceForge\footnote{\url{https://en.wikipedia.org/wiki/SourceForge}},
which once dominated the open source repository space in the way that GitHub does today \cite{Tamburri2020}).

When you create projects on hosted services,
use a team account as the project owner rather than a personal account.
Doing this makes it easier to give other people permission to manage the project,
and as noted in Tip~6,
a project with multiple owners from different institutions
is harder for any one institution to lock down.
For the same reason,
do not rely solely on logins or email addresses associated with your institution:
instead,
ask yourself if you will still have access to the project if you lose that identity,
and add an identity you personally control to the team that owns the project.
You can also add your \href{https://orcid.org/}{ORCID} to the project's metadata
so that the project links to a profile that you control
even when your contact address changes.

\begin{quote}
  \noindent
  \textbf{What's in a project?}

  When deciding what to store where,
  remember that your version control repository only stores part of what makes up your project.
  For example,
  while GitHub wikis are stored in ordinary git repositories, the issues and discussions live in GitHub's internal database;
  you can use the GitHub API to download their content,
  but (a) the result is intended for consumption by machines, not people,
  and (b) if you are doing this on short notice,
  the odds are high that other people are trying to do it at the same time.
  GitHub's servers may not be able to manage that load when you need them to,
  so use tools like \href{https://github.com/jlord/offline-issues}{offline-issues}
  to save hosted content as plain-text files regularly.
\end{quote}

\item
  Create a DOI for each release of your software
  to ensure citability and retrievability even if the project repository becomes unavailable,
  and add a \href{https://citation-file-format.github.io/}{Citation.CFF}
  or \href{https://codemeta.github.io}{codemeta.json} file to your code \cite{Druskat2021}
  containing citation metadata.
  Tools such as \href{https://citation-file-format.github.io/cff-initializer-javascript/}{cffinit},
  \href{https://codemeta.github.io/codemeta-generator/}{codemeta generator},
  and \href{https://github.com/citation-file-format/citation-file-format/blob/main/README.md\#tools-to-work-with-citationcff-files-wrench}{others}
  can help you do this.

## Community

Project culture encompasses the unwritten rules, shared values, and working practices that make projects successful and sustainable. Document the core values and principles that guide decision-making, including examples of how these values are applied in practice and why they matter to the project's success. Identify cultural practices, traditions, and communication norms that contribute to positive team dynamics and project effectiveness. Discuss with successors how to maintain positive cultural elements while allowing for natural evolution and improvement. Consider creating informal mentorship opportunities or advisory roles that help preserve institutional memory while empowering new leadership to develop their own approach.

Research collaborations often span multiple years and involve complex interpersonal and institutional relationships that require careful management during transitions. Review all active collaborations to assess their status, remaining obligations, and the level of personal relationship involved in maintaining the partnership. Communicate with collaborators about leadership changes early enough to allow for relationship building with successors while ensuring continuity of shared work. Document the history and context of each collaboration, including informal agreements, communication preferences, and any ongoing tensions or issues that may not be immediately apparent. Consider facilitating introduction meetings between collaborators and successors to establish personal connections that support continued partnership.

Crisis situations that threaten project continuity require pre-established communication protocols and emergency contacts to enable rapid response and coordination. Develop emergency contact lists that include key stakeholders, service providers, institutional contacts, and team members, ensuring that multiple people have access to this information. Establish clear communication hierarchies and decision-making authorities for different types of emergencies, from technical failures to personnel crises to external threats. Create template communications for common emergency scenarios that can be quickly customized and deployed through multiple channels including email, social media, and direct phone contact. Test emergency communication procedures periodically and update contact information regularly to ensure effectiveness when crisis situations actually occur.

## Community Adoption

Publishing your code is not the same as publicizing it.
The more people who know about and rely on your project,
the greater the chances that someone will help keep it alive,
whether by working on it directly or supporting you in doing so.
If you have not named your project yet,
choose a name that does not hint at direct and exclusive affiliation to a single institution.
This can help if the code needs to be relocated,
and also makes contributors from other institutions feel welcome.
Additionally,
label entry-level issues
(e.g., to use the ``good first issue'' label on GitHub)
so that people can easily find a place to start \cite{Steinmacher2015}.

Going further,
there is a causal link between social media mentions and both new adopters and new contributors \cite{Fang2022}.
Announcing your project on mailing lists, forums, or social media,
and talking about it at conferences are therefore necessary but not sufficient:
since everyone else is doing this too,
it is hard to be heard above the noise.

There are many good guides to what you can do to promote your project \cite{Kuchner2011,BelliniSaibene2024}.
A short video showing how to use the software
or a slide deck that others can incorporate into their lectures
will increase uptake by lowering the cost of adoption.
Similarly,
a one-page website that opens with an elevator pitch
explaining who the software is for
and how it will improve their lives
is much more likely to lead to that crucial ``second glance''
than a list of publications.

Disseminating your code through tutorials at conferences is another effective strategy.
Tutorials are an opportunity for you,
as an author,
to describe your work in depth
and (more importantly) convince your audience to use it.
Networking through such events will enable you to build relationships with
the people most likely to care about your project,
and it is the best way to ensure that you land well after you leave your current position.

<div class="callout" markdown="1">

If you can,
have at least one person outside your organization commit to your code.
Such community contributions lead to joint ownership of intellectual property,
which makes it harder for any single institution to lock down your work.
You can reinforce this by adding their name to the copyright statement in your license.

</div>

Finally,
remember that it is not all about \emph{your} project.
If you ask others to help maintain your code,
be prepared to give them something in return:
a letter of reference,
help testing or documenting their project,
or co-authorship credit on the project and associated publications.
