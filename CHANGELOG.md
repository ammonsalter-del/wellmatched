# Changes

## 1.1, 29 October 2026

Before the first public release, after a day of testing with real runs.

- Journal buckets (World leading, Leading, Excellent, Strong) in place of any list's raw grades; the sources are cited and not endorsed.
- The level a department hires at is worked out by the page from its recent hires' records (OpenAlex, or the journals on their staff pages), with the school's own place blended in where only one or two people have records.
- Each department reading names a recent hire and what the pages show they arrived with.
- Status: a candidate from a school two or more levels above the department is read as a rare move; a school one step below the PhD school is read as a common move, with no question about coming and staying.
- The research record carries more weight, and institutional status less, for candidates whose PhD school is not at the top; the job market paper square no longer counts towards the score; revise-and-resubmits count 30, 45 and 60 per cent of a published paper by round.
- Searches cost less: fewer fetches, places and wild cards run alongside the readings, prompt caching. One department with Find it for me is about $1.20 and seven minutes.
- The Well Matched family: Use an API (this site), Do it yourself (the Claude artifact), In your Claude (your own chat).
- Google Analytics on the website only, behind a consent notice, recording use by country and time and nothing else.
- 30 October: an "FAQs about Well Matched" box under the privacy box, in the developer's own words: why use the tool, why trust its reading, where it falls short, that it is not a judgement of the person, what to expect if part of it does not feel supportive, bias and personal characteristics, a PhD from outside Europe or from an unranked school, and whether material is used to train the AI.
- 30 October: department readings open with the committee's view of the file, then the evidence from the pages, with a recent hire named.
- 30 October: the career-break note is shorter and follows the European Research Council's principle; the privacy wording says the tool itself keeps nothing and that materials go to Anthropic under the user's own account settings; the intro and footer say the tool shows how a committee is likely to assess you and is built on experience of how committees assess candidates.

## 1.0, 28 October 2026

First public release.

- The tool (`index.html`), run with your own Anthropic API key.
- Well Matched in your Claude, the version for your own Claude chat (`in-your-claude/`).
- The development manual (`manual.md`).
