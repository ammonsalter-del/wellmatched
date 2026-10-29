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

## How it was built and checked

Well Matched began in October 2026 as a Claude artifact, drawing on experience of hiring committees, and was revised many times. All materials created with Claude Opus 5.5, with review by Ammon Salter.

Beta-testers, named under Credits, used it and commented. Their comments shaped the questions it asks and led to the agents that find each department's information. It was then rebuilt as a website that runs on the candidate's own key. The scores come from fixed rules in the page, and Claude does the reading.

It was checked in four ways:

- **Invented candidates.** More than twenty, from schools of different standing and countries, with different records and ambitions, were run against invented departments: about 30 cases in all. The Do it yourself version was also run on an invented candidate in a Claude account.
- **Stand-in tests.** A browser loads the page and answers in place of Anthropic and OpenAlex with fixed replies, so the scoring, wording, safeguards, layout and report can be checked at no cost. Some tests feed in faults on purpose, such as hype or an invented professor, to check that the page removes them.
- **Critical reviews.** Three reviewers, played by Claude, read the page and the manual from different points of view: someone from a lower-ranked school, a senior professor and an information systems scholar. The manual lists what changed as a result.
- **Sources.** The references were checked against Crossref, and the links to the lists and rankings against their own pages.

It has not yet been tested against real hiring outcomes. Full details are in the [development manual](manual.html), under How it was developed, Testing and What the reviewers said.

## Your data

Nothing you enter is captured or recorded, and there is no database behind the tool. There is no advertising, no fee and no paid version. What you put in goes only to Anthropic, with your own key, to be read, and what happens to it there is between you and the settings you choose in your Anthropic account. The names of departments' staff are sent to OpenAlex to count their publications.

## Disclaimer

Well Matched gives an indication, not advice. It cannot know how any committee will decide and makes no promise about any application. Use it as one view among others, alongside advice from your supervisor and colleagues. The developer accepts no responsibility for decisions made using it.

## Licence

Well Matched is shared under the [Creative Commons Attribution-NonCommercial 4.0 International licence (CC BY-NC 4.0)](LICENSE.md): you are free to use, adapt and share it for non-commercial purposes, with credit to Well Matched and its contributors. The PDF and Word readers in `lib/` keep their own licences (Apache 2.0 for pdf.js, BSD 2-Clause for mammoth.js). The licence covers Well Matched's own code, text and journal buckets; the lists and rankings named as sources belong to their publishers and keep their own terms. No grade from any of them is kept here.

## Sources

The journal buckets (World leading, Leading, Excellent, Strong) and the school scores are Well Matched's own. They combine these published lists and rankings, and no grade or rank from any of them is shown or kept.

- **Journals:** Anne-Wil Harzing's Journal Quality List and the lists it compiles that we use (the Chartered ABS Academic Journal Guide, VHB, FNEGE, CNRS, Hcéres and the Danish BFI list), with the UT Dallas and FT50 journal lists.
- **Schools:** the UT Dallas research rankings, the QS subject ranking for business and management, the QS World University Rankings, the FT Research Insights ranking and REF 2021.

If you think a journal or school is placed wrongly, please take it up with the list or ranking makers. Full citations, with links, are in the [development manual](manual.html), under Sources and credits.

**A note on status hierarchies.** Journal lists and school ranking tables are status hierarchies built on reputation: what people in the field believe, not what is true. We do not endorse them, and they are unreliable for judging individual people, departments or even universities. Committees are made up of people, just like you. Hiring early-career academics is hard, and in the face of uncertainty committees often fall back on weak signals of status. They may not consult the lists or ranking tables directly, but they are highly likely to be aware of them. Well Matched draws on these hierarchies to show how a committee is likely to read a record, not how it should be read. It looks only at shortlisting, the first stage; later stages bring in other factors, such as the presentation, interviews and local preferences. See the development manual, under The limits of the tool and Related research, for further details.

## Related research

There is a broad literature on decision making in panels and committees, on journal lists and on status. A short review, with references, is in the [development manual](manual.html), under Related research.

## How to cite

Salter, A. (2026). *Well Matched: matching first-post candidates with European business school departments* [Software]. Zenodo. https://doi.org/[DOI to be added]

## Credits

Developed by Ammon Salter, Warwick Business School. All materials created with Claude Opus 5.5, with review by Ammon Salter.

Contributors and beta-testers: Federico Bignone (Warwick Business School), Christos Kolympiris (Warwick Business School), Rossella Salandra (University of Bath), Philipp Wähler (CUNEF) and Zou Na (University of Bath). They tried the tool and gave feedback. Any errors are the developer's own.

Suggestions, experiments and experiences, positive or negative, are welcome: [ammon.salter@wbs.ac.uk](mailto:ammon.salter@wbs.ac.uk).
