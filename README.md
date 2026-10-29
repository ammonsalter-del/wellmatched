# Well Matched

![Well Matched](images/well-matched-logo.png)

**See your record through a hiring committee's eyes.** Well Matched is for PhD students and postdocs looking for their first teaching and research post at a business school in Europe. It reads your CV, letter and job market paper the way a shortlisting committee might, searches the schools' own websites, and shows how well you match each department you are considering, and why.

**Free, open source and private.** The developer sees nothing you enter, and nothing it tells you. There is no server and nothing is kept: the page runs in your own browser, and your materials go only to Anthropic, using your own API key, to be read.

[Open Well Matched](https://[GITHUB PAGES ADDRESS TO BE ADDED]/) · [Development manual](manual.html)

## What you get

- for each department you name, a score out of 100 and a reading of how its committee might see you, square by square;
- what might hold you back there, how to make your case, and what could change it;
- other schools worth a look, including wild cards you may not have considered;
- a report to keep, with every piece of material used.

It reflects experience, not an ideal: it is designed to show how hiring committees tend to behave, not how they ought to. AI can make mistakes, so check what it tells you.

## How to use it

**With your own Anthropic API key.** Open the tool, paste a key from [console.anthropic.com](https://console.anthropic.com) (you will need to add credit there first), add your materials and up to three departments, and press Read my match. A run with three departments costs about $1.50 to $1.70, charged to your own Anthropic account, and takes about five minutes. It is safest to make a key just for this tool and set a monthly spending limit on it.

**In your Claude.** You can also run Well Matched, with its web searches, through your own personal or professional Claude account: see [Well Matched in your Claude](in-your-claude/). Attach `in-your-claude/well-matched-chat.html` to a new Claude chat and follow `in-your-claude/How to run Well Matched in your Claude chat.txt`.

**Do it yourself.** A shorter version runs as a Claude artifact on your own Claude account, with no key. You paste what you know about each department, and it does not search the web. It is likely to be less reliable than the other versions, as it has less information to work with: the logic is the same, but the readings may vary more. [link]

**On your own computer.** Download this repository and serve the folder with any small web server, for example:

```
python3 -m http.server 8000
```

then open `http://localhost:8000/` in your browser. (Opening `index.html` straight from the file system may stop the PDF reader from working.)

## What is in this repository

- `index.html`: the tool, a single page.
- `lib/`: the PDF and Word readers it uses (pdf.js and mammoth.js), kept here so nothing is loaded from elsewhere.
- `images/`: the logo, the picture of how it works, and the detailed map.
- `manual.html` and `manual.md`: the development manual, which explains how the tool works, how it scores and the rules it follows.
- `in-your-claude/`: Well Matched in your Claude, the version for your own Claude chat, with its instructions.
- `SECURITY.md`: how your key and materials are handled, and how to report a problem.
- `CONTRIBUTING.md` and `CHANGELOG.md`: how to send suggestions or changes, and what has changed.

## Your data

Nothing you enter is captured or recorded, and there is no database behind the tool. There is no advertising, no fee and no paid version. What you put in goes only to Anthropic, with your own key, to be read, and what happens to it there is between you and the settings you choose in your Anthropic account. The names of departments' staff are sent to OpenAlex to count their publications.

## Disclaimer

Well Matched gives an indication, not advice. It cannot know how any committee will decide and makes no promise about any application. Use it as one view among others, alongside advice from your supervisor and colleagues. The developer accepts no responsibility for decisions made using it.

## Licence

Well Matched is shared under the [Creative Commons Attribution-NonCommercial 4.0 International licence (CC BY-NC 4.0)](LICENSE.md): you are free to use, adapt and share it for non-commercial purposes, with credit to Well Matched and its contributors. The PDF and Word readers in `lib/` keep their own licences (Apache 2.0 for pdf.js, BSD 2-Clause for mammoth.js). The licence covers Well Matched's own code, text and journal buckets; the lists and rankings named as sources belong to their publishers and keep their own terms. No grade from any of them is kept here.

## Sources

Well Matched draws on published journal lists and school rankings. The journal buckets (World leading, Leading, Excellent, Strong) and the school scores are Well Matched's own, and no grade or rank from any list is shown or kept. If you think a journal or school is placed wrongly, please take it up with the list or ranking makers; when their lists change, Well Matched will follow. The development manual explains how the sources are combined, under How the score is made and The school data.

**A note on status hierarchies.** Journal lists and school ranking tables are status hierarchies built on reputation: what people in the field believe, not what is true. We do not endorse them, and they are unreliable for judging individual people, departments or even universities. Committees are made up of people, just like you. Hiring early-career academics is hard, and in the face of uncertainty committees often fall back on weak signals of status. They may not consult the lists or ranking tables directly, but they are highly likely to be aware of them. Well Matched draws on these hierarchies to show how a committee is likely to read a record, not how it should be read. It looks only at shortlisting, the first stage; later stages bring in other factors, such as the presentation, interviews and local preferences. See the development manual, under The limits of the tool and Related research, for further details.

<details>
<summary>The sources in full</summary>

Journals. The journal buckets (World leading, Leading, Excellent, Strong) are Well Matched's own. We draw on Anne-Wil Harzing's Journal Quality List and on each of the lists it compiles that we use, together with the UT Dallas and FT lists. No grade from any list is shown or kept.

- Harzing, A.-W. (2026). Journal Quality List, 72nd edition, 27 March 2026. <https://harzing.com/resources/journal-quality-list>
- Chartered Association of Business Schools (2024). Academic Journal Guide 2024. <https://charteredabs.org/academic-journal-guide/academic-journal-guide-2024>
- VHB, German Academic Association for Business Research (2024). VHB Publication Media Rating 2024. <https://www.vhbonline.org/en/services/vhb-rating-2024>
- FNEGE (2025). Classement des revues scientifiques en sciences de gestion et management 2025. <https://fnege.org/classement-des-revues-scientifiques-en-sciences-de-gestion/>
- CNRS, Section 37 Économie et Gestion (2020). Catégorisation des revues en Économie et en Gestion, version 5.07, June 2020. <https://www.gate.cnrs.fr/wp-content/uploads/2021/12/categorisation37_liste_juin_2020-2.pdf>
- Hcéres (2021). Liste des revues, SHS1 Économie et gestion, 9 July 2021. <https://www.hceres.fr/en/node/1902>
- Danish Ministry of Higher Education and Science (2021). BFI authority list of series (Den Bibliometriske Forskningsindikator), final edition 2021; no longer online.
- Naveen Jindal School of Management, UT Dallas. The 24 journals of the UTD Top 100 Business School Research Rankings. <https://jsom.utdallas.edu/the-utd-top-100-business-school-research-rankings/>
- Financial Times. The 50 journals used in FT rankings (FT50). <https://www.ft.com/content/db863a0a-6524-45f9-bc52-fee997634bdc>

Schools. Each school's score is Well Matched's own, a composite of these sources, banded, and adjusted where needed to reflect academic reputation in business schools and universities not captured by these lists. For UK schools, the REF 2021 grade point average is used to correct cases where QS places a school well above its REF result. No rank from any source is shown or kept.

- Naveen Jindal School of Management, UT Dallas. UTD Top 100 Business School Research Rankings, worldwide, 2021 to 2025. <https://jsom.utdallas.edu/the-utd-top-100-business-school-research-rankings/worldRankings>
- QS Quacquarelli Symonds (2026). QS World University Rankings by Subject 2026: Business and Management Studies (academic reputation). <https://www.topuniversities.com/university-subject-rankings/business-management-studies>
- QS Quacquarelli Symonds (2025). QS World University Rankings 2026 (used for the list of world-leading universities). <https://www.topuniversities.com/world-university-rankings/2026>
- Financial Times (2025). FT Research Insights ranking 2025. <https://www.ft.com/content/a84f7e35-e062-4a47-8da2-5e11efb3f05c>
- REF 2021. Results, Unit of assessment 17: Business and Management Studies. <https://results2021.ref.ac.uk/profiles/units-of-assessment/17>

</details>

## Related research

Selection under uncertainty has been a long-running theme in our own work. Studying the panels of a large professional services firm, we found that evaluators favour projects of intermediate novelty, and that their appetite for novelty falls when they are busy and rises when the panel holds more varied expertise or sits close to the applicant (Criscuolo et al., 2017). Using the random order in which those projects were reviewed, we showed that a proposal heard straight after a funded one is less likely to be funded itself, as evaluators' mental and emotional resources run down over a meeting (Criscuolo et al., 2021). At the UK's largest research council, panels are less likely to fund a marginal application when another from the same institution has already been funded in that round, which suggests a preference for spreading awards across institutions (Lawson & Salter, 2023). Journal lists carry a status of their own. UK business and management academics would give up citations to publish in a 4* rather than a 4-rated journal, and those who already hold such papers, or who work at higher-ranked institutions, would give up the most (Salandra et al., 2022). Reliance on the ABS list is heaviest among academics with less influence in their field and among those at middle- and lower-status universities (Walker, Fenton, et al., 2019), and attitudes towards the list soften among those whose journals are upgraded (Walker, Salter, et al., 2019). A higher grade also brings more citations: when a journal moved up the ABS list, citations to its papers rose, largely because authors cite highly ranked journals to signal the standing of their own work (Drivas & Kremmydas, 2020). Critics argue that such lists narrow what the field studies (Mingers & Willmott, 2013; Tourish & Willmott, 2015) and that counts of 4-rated papers have come to dominate how deans and research managers judge staff and job applicants (Hussain, 2015). Others defend the lists. Foss and Mol (2026) argue that they are less imperfect than the alternatives, offering a scalable and at least partly meritocratic way to move beyond networks, prestige and patronage, while warning against using them as the only measure of quality.

Beyond our own work, Lamont (2009) shows how academic panels define and recognise quality in their deliberations. Status brings rewards of its own (Merton, 1968; Podolny, 1993), although separating the effect of status from that of quality is difficult (Azoulay et al., 2014). Prato et al. (2024) review a decade of research on status and distinguish three types: prestige status, based on merit; iconic status, based on symbols; and dominant status, based on power. All three may be present in academic rankings and status hierarchies.

We use this material to try to uncover how committees think, not how they should. Well Matched looks only at shortlisting. Later in the hiring process other factors come into play, such as the quality of the presentation, personal meetings, answers at interview, local preferences and past hiring rounds. It is a complex cocktail of factors at each stage. We focus on the first stage here.

References

- Azoulay, P., Stuart, T., & Wang, Y. (2014). Matthew: Effect or fable? *Management Science, 60*(1), 92–109. [https://doi.org/10.1287/mnsc.2013.1755](https://doi.org/10.1287/mnsc.2013.1755)
- Criscuolo, P., Dahlander, L., Grohsjean, T., & Salter, A. (2017). Evaluating novelty: The role of panels in the selection of R&D projects. *Academy of Management Journal, 60*(2), 433–460. [https://doi.org/10.5465/amj.2014.0861](https://doi.org/10.5465/amj.2014.0861)
- Criscuolo, P., Dahlander, L., Grohsjean, T., & Salter, A. (2021). The sequence effect in panel decisions: Evidence from the evaluation of research and development projects. *Organization Science, 32*(4), 987–1008. [https://doi.org/10.1287/orsc.2020.1413](https://doi.org/10.1287/orsc.2020.1413)
- Drivas, K., & Kremmydas, D. (2020). The Matthew effect of a journal's ranking. *Research Policy, 49*(4), Article 103951. [https://doi.org/10.1016/j.respol.2020.103951](https://doi.org/10.1016/j.respol.2020.103951)
- Foss, N. J., & Mol, M. (2026, May 13). Journal lists advance both rigour and relevance. *Times Higher Education*. [https://www.timeshighereducation.com/opinion/journal-lists-advance-both-rigour-and-relevance](https://www.timeshighereducation.com/opinion/journal-lists-advance-both-rigour-and-relevance)
- Hussain, S. (2015). Journal list fetishism and the "sign of 4" in the ABS guide: A question of trust? *Organization, 22*(1), 119–138. [https://doi.org/10.1177/1350508413506763](https://doi.org/10.1177/1350508413506763)
- Lamont, M. (2009). *How professors think: Inside the curious world of academic judgment*. Harvard University Press. [https://doi.org/10.4159/9780674054158](https://doi.org/10.4159/9780674054158)
- Lawson, C., & Salter, A. (2023). Exploring the effect of overlapping institutional applications on panel decision-making. *Research Policy, 52*(9), Article 104868. [https://doi.org/10.1016/j.respol.2023.104868](https://doi.org/10.1016/j.respol.2023.104868)
- Merton, R. K. (1968). The Matthew effect in science. *Science, 159*(3810), 56–63. [https://doi.org/10.1126/science.159.3810.56](https://doi.org/10.1126/science.159.3810.56)
- Mingers, J., & Willmott, H. (2013). Taylorizing business school research: On the "one best way" performative effects of journal ranking lists. *Human Relations, 66*(8), 1051–1073. [https://doi.org/10.1177/0018726712467048](https://doi.org/10.1177/0018726712467048)
- Podolny, J. M. (1993). A status-based model of market competition. *American Journal of Sociology, 98*(4), 829–872. [https://doi.org/10.1086/230091](https://doi.org/10.1086/230091)
- Prato, M., Ertug, G., Castellucci, F., & Zou, T. (2024). The status of status research: A review of the types, functions, levels, and audiences. *Journal of Management, 50*(6), 2266–2308. [https://doi.org/10.1177/01492063241226918](https://doi.org/10.1177/01492063241226918)
- Salandra, R., Salter, A., & Walker, J. T. (2022). Are academics willing to forgo citations to publish in high-status journals? Examining preferences for 4* and 4-rated journal publication among UK business and management academics. *British Journal of Management, 33*(3), 1254–1270. [https://doi.org/10.1111/1467-8551.12510](https://doi.org/10.1111/1467-8551.12510)
- Tourish, D., & Willmott, H. (2015). In defiance of folly: Journal rankings, mindless measures and the ABS Guide. *Critical Perspectives on Accounting, 26*, 37–46. [https://doi.org/10.1016/j.cpa.2014.02.004](https://doi.org/10.1016/j.cpa.2014.02.004)
- Walker, J. T., Fenton, E., Salter, A., & Salandra, R. (2019). What influences business academics' use of the Association of Business Schools (ABS) list? Evidence from a survey of UK academics. *British Journal of Management, 30*(3), 730–747. [https://doi.org/10.1111/1467-8551.12294](https://doi.org/10.1111/1467-8551.12294)
- Walker, J. T., Salter, A., Fontinha, R., & Salandra, R. (2019). The impact of journal re-grading on perception of ranking systems: Exploring the case of the Academic Journal Guide and Business and Management scholars in the UK. *Research Evaluation, 28*(3), 218–231. [https://doi.org/10.1093/reseval/rvz010](https://doi.org/10.1093/reseval/rvz010)

## How to cite

Salter, A. (2026). *Well Matched: matching first-post candidates with European business school departments* [Software]. Zenodo. https://doi.org/[DOI to be added]

## Credits

Developed by Ammon Salter, Warwick Business School.

Contributors and beta-testers: Federico Bignone (Warwick Business School), Christos Kolympiris (Warwick Business School), Rossella Salandra (University of Bath), Philipp Wähler (CUNEF) and Zou Na (University of Bath). They tested the tool and commented on it; they are not responsible for the tool or anything it tells you.

Suggestions, experiments and experiences, positive or negative, are welcome: [ammon.salter@wbs.ac.uk](mailto:ammon.salter@wbs.ac.uk).
