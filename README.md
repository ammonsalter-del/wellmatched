# Well Matched

![Well Matched](images/well-matched-logo.png)

**See your record through a hiring committee's eyes.** Well Matched is for PhD students and postdocs looking for their first teaching and research post at a business school in Europe. It reads your CV, letter and job market paper the way a shortlisting committee might, searches the schools' own websites, and shows how well you match each department you are considering, and why.

**Free, open source and private.** Everything runs in your browser. Your materials go only to Anthropic, with your own API key, under your own account's settings. The tool itself keeps nothing.

[Open Well Matched](https://ammonsalter-del.github.io/wellmatched/)

## What you get

- for each department you name, a score out of 100 and a reading of how its committee might see you, square by square;
- what might hold you back there, how to make your case, and what could change it;
- other schools worth a look, including wild cards you may not have considered;
- a report to keep, with every piece of material used.

It is built on experience of how hiring committees assess candidates. AI can make mistakes, so check what it tells you.

## How to use it

**With your own Anthropic API key.** Open the tool, paste a key from [console.anthropic.com](https://console.anthropic.com) (you will need to add credit there first), add your materials and up to three departments, and press Read my match. A run on one department with Find it for me costs about $1.20 and takes about seven minutes; three departments come to about $2.50 and ten to twelve minutes, charged to your own Anthropic account (measured on 29 October 2026). It is safest to make a key just for this tool and set a monthly spending limit on it.

**With your Claude.** You can also run Well Matched, with its web searches, through your own personal or professional Claude account: see [Well Matched with your Claude](in-your-claude/). Attach `in-your-claude/well-matched-chat.html` to a new Claude chat and follow `in-your-claude/How to run Well Matched in your Claude chat.txt`.

**Do it yourself.** A shorter version runs as a Claude artifact on your own Claude account, with no key. You paste what you know about each department, and it does not search the web, so it has less to work with than the other versions: the logic is the same. [Open the artifact](https://claude.ai/artifact/J8AQ5XHqGiMXQLfXtuEcnf).

**On your own computer.** Download this repository and serve the folder with any small web server, for example:

```
python3 -m http.server 8000
```

then open `http://localhost:8000/` in your browser. (Opening `index.html` straight from the file system may stop the PDF reader from working.)

## What is in this repository

- `index.html`: the tool, a single page.
- `lib/`: the PDF and Word readers it uses (pdf.js and mammoth.js), kept here so nothing is loaded from elsewhere.
- `images/`: the logo, the picture of how it works, and the detailed map.
- `manual.md`: the development manual, which explains how the tool works, how it scores and the rules it follows.
- `in-your-claude/`: Well Matched with your Claude, the version for your own Claude chat, with its instructions.
- `SECURITY.md`: how your key and materials are handled, and how to report a problem.
- `CONTRIBUTING.md` and `CHANGELOG.md`: how to send suggestions or changes, and what has changed.

## How it was built and checked

Well Matched began in October 2026 as a Claude artifact, drawing on experience of hiring committees, and was revised many times. Designed, developed and reviewed by Ammon Salter, Warwick Business School, using Claude Opus 5.5 and Claude Fable 5.1.

Beta-testers, named under Credits, used it and commented. Their comments shaped the questions it asks and led to the agents that find each department's information. It was then rebuilt as a website that runs on the candidate's own key. The scores come from fixed rules in the page, and Claude does the reading.

It was checked in four ways:

- **Invented candidates.** More than twenty, from schools of different standing and countries, with different records and ambitions, were run against invented departments: about 30 cases in all. The Do it yourself version was also run on an invented candidate in a Claude account.
- **Stand-in tests.** A browser loads the page and answers in place of Anthropic and OpenAlex with fixed replies, so the scoring, wording, safeguards, layout and report can be checked at no cost. Some tests feed in faults on purpose, such as hype or an invented professor, to check that the page removes them.
- **Critical reviews.** Three reviewers, played by Claude, read the page and the manual from different points of view: someone from a lower-ranked school, a senior professor and an information systems scholar.
- **Sources.** The references were checked against Crossref, and the links to the lists and rankings against their own pages.

## FAQs about Well Matched

The same questions and answers as on the website.

**Why use this?** You are about to apply for your first post, and you cannot see how a committee will read your file. Most people apply everywhere, which costs time and rarely works. Well Matched reads your materials and each department's own pages the way a shortlisting committee is likely to, and tells you where you fit, where you do not yet, and what to say to each one.

**Why should I trust its reading?** Committees make decisions under uncertainty. A complex cocktail of factors shapes their choices, and within it status hierarchies, journal lists and school rankings act as weak signals. Well Matched draws on those signals to show how a committee is likely to read a record.

**Where does it fall short?** It is AI, and it makes mistakes. The search can miss people on a school's pages, and the readings vary a little from one run to the next, so a point or two of difference means nothing. It knows European business schools and only the shortlisting stage; interviews and local preferences come later. Check what it found before you read its verdict, and weigh it alongside the advice of your supervisor and colleagues.

**How well has it been tested?** Not extensively. Well Matched is a prototype. The rules come from the developer's experience and have been checked against invented candidates and by beta-testers with their own materials, but not against real hiring outcomes. Comments are welcome.

**Is this a judgement of me?** No. You are talented and capable, and the tool is there to tell you how others read materials about you, which is a different thing. Academic careers are long, and as yours develops the judgements will shift from where you trained to what you have done. Where people start in the academic labour market is rarely where they end, and there are many pathways. The developer finished a DPhil at the Science Policy Research Unit, with no publications. It was a wonderful training, but it would have got a poor match at many business schools.

**What if part of it does not feel supportive?** The tool is meant to be developmental and supportive, since applying for a first academic post is stressful enough. The developer has tried to hold it to that tone, but AI models can drift. Please remember that the readings are generated by AI, which is a machine.

**Does it allow for bias?** No. Well Matched makes no allowance for the biases a committee may hold about nationality, race, gender or any other personal characteristic, what the law often calls protected characteristics. Since AI is trained on human data, its reading may carry implicit human biases of its own. The tool does not ask for your personal characteristics, and it is best not to give it any. It does take some account of language skills and reasons for moving, but these count only at the margin. In the developer's experience, academic committees try to be fair. For career breaks it follows the same principle as the European Research Council, extending the window of assessment by a year for every significant break.

**Why does it score whether senior staff would warm to me?** Committees tend to favour people like themselves, so the tool takes account of it. It is a small part of the overall evaluation.

**Why does it name real people?** The readings name a department's staff from the school's own pages and their publication records, which are public. Nothing about anyone is kept.

**What if my PhD is from outside Europe?** Your PhD school is placed from worldwide rankings, so it counts in the same way as any other. The departments it reads, and the places and wild cards it suggests, are European business schools, which is what the tool knows.

**What if my PhD school is not in the rankings?** PhD training is shown as No information and left out of the score, the status square is left to Claude's reading of the department, and no places or wild cards can be suggested from the rankings.

**Was personal data used to build it?** No personal data or real cases were used in making the tool. It rests on public rankings and lists, the developer's own knowledge and experience, comments from beta-testers on their experience of using it with their own materials, and many runs with fictional personas.

**Is this a university tool?** No. Nothing from Warwick Business School went into it, the university does not use it, and no university should: it is for students, not committees. It endorses no list or ranking. It shares one person's experience of how applicants are assessed, gathered at several universities over many rounds of shortlisting for different roles, and it is informed by research on the topic.

**Is my material used to train the AI?** Not by default. On this website your material goes to Anthropic through its API, and Anthropic says it does not use what is sent that way to train its models unless you choose to let it. In the versions that run through a Claude account, it depends on the account's setting, Help improve our AI models, under Privacy. Anthropic sets this out in its [page on model training](https://privacy.claude.com/en/articles/7996868-is-my-data-used-for-model-training), its [commercial terms](https://www.anthropic.com/legal/commercial-terms) for the API and its [note on the account setting](https://privacy.claude.com/en/articles/12109829-how-do-i-change-my-model-improvement-privacy-settings). The tool itself keeps nothing, and your key, if you ask the page to remember it, stays only in this browser.

## Your data

The tool itself captures and records nothing, and there is no database behind it. There is no advertising, no fee and no paid version. What you put in goes only to Anthropic, with your own key, to be read, and what happens to it there is between you and the settings you choose in your Anthropic account. The names of departments' staff are sent to OpenAlex to count their publications. On the website, the page tells a counter, GoatCounter, when it is opened, when a run finishes and when a file is downloaded, with the country and the time, and nothing else; it sets no cookie and keeps no address.

## Disclaimer

Well Matched is built on experience of how hiring committees assess candidates. This tool gives an indication, not advice. It cannot know how any committee will decide and makes no promise about any application. Use it as one view among others, alongside advice from your supervisor and colleagues. The developer accepts no responsibility for decisions made using it.

No personal data or real cases were used in making the tool: it rests on public rankings and lists, the developer's own knowledge and experience, comments from beta-testers on their experience of using it with their own materials, and many runs with fictional personas.

Nothing from Warwick Business School went into it, the university does not use it, and no university should: it is for students, not committees.

This tool is a prototype. It is designed to help, but it is AI based and therefore is imperfect and makes mistakes. Each hiring round is different, and each candidate is different.

## Licence

Well Matched is shared under the [Creative Commons Attribution-NonCommercial 4.0 International licence (CC BY-NC 4.0)](LICENSE.md): you are free to use, adapt and share it for non-commercial purposes, with credit to Well Matched and its contributors. The PDF and Word readers in `lib/` keep their own licences (Apache 2.0 for pdf.js, BSD 2-Clause for mammoth.js). The licence covers Well Matched's own code, text and journal buckets; the lists and rankings named as sources belong to their publishers and keep their own terms. No grade from any of them is kept here.

## Sources

The journal buckets (World leading, Leading, Excellent, Strong) and the school scores are Well Matched's own. They combine these published lists and rankings, and no grade or rank from any of them is shown or kept. Using them implies no endorsement either way: their makers have not endorsed Well Matched, and Well Matched does not endorse them.

- **Journals:** Anne-Wil Harzing's Journal Quality List and the lists it compiles that Well Matched uses (the Chartered ABS Academic Journal Guide, VHB, FNEGE, CNRS, Hcéres and the Danish BFI list), with the UT Dallas and FT50 journal lists.
- **Schools:** the UT Dallas research rankings, the QS subject ranking for business and management, the QS World University Rankings, the FT Research Insights ranking and REF 2021.

If you think a journal or school is placed wrongly, please take it up with the list or ranking makers. Full citations, with links, are on the tool page, under Sources.

**A note on status hierarchies.** Journal lists and school ranking tables are status hierarchies built on reputation: what people in the field believe, not what is true. Well Matched does not endorse them, and they are unreliable for judging individual people, departments or even universities. Committees are made up of people, just like you. Hiring early-career academics is hard, and in the face of uncertainty committees often fall back on weak signals of status. They may not consult the lists or ranking tables directly, but they are highly likely to be aware of them. Well Matched draws on these hierarchies to show how a committee is likely to read a record, not how it should be read. It looks only at shortlisting, the first stage; later stages bring in other factors, such as the presentation, interviews and local preferences.

## How to cite

Salter, A. (2026). *Well Matched: matching first-post candidates with European business school departments* [Software]. Zenodo. https://doi.org/[DOI to be added]

## Credits

Designed, developed and reviewed by Ammon Salter, Warwick Business School, using Claude Opus 5.5 and Claude Fable 5.1. Website: [ammonsalter.org](https://ammonsalter.org).

If you teach entrepreneurship or innovation, you might like to use the games from [The I&E Playbook](https://ieplaybook.substack.com).

Contributors and beta-testers: Federico Bignone, Christos Kolympiris, Rossella Salandra, Philipp Wähler and Zou Na. They tried the tool and gave feedback. Any errors are the developer's own.

Suggestions, experiments and experiences, positive or negative, are welcome: [ammon.salter@wbs.ac.uk](mailto:ammon.salter@wbs.ac.uk).
