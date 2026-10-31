# Security

## Supported versions

| Version | Supported |
| ------- | --------- |
| 1.x     | Yes       |

## How Well Matched handles your information

Well Matched is a single web page with no server, no database and no account. It runs in your own browser. It comes in three versions (see The Well Matched family on the tool page); this file covers all three.

### Use an API (the website)

- **Your API key** is typed into the page and sent only to Anthropic (`api.anthropic.com`), with each request to read your materials. It is never sent anywhere else. If you tick "Remember my key on this computer", it is kept in this browser's local storage on this computer; "Forget my key" removes it. On a shared computer, do not tick it.
- **Your materials** (CV, letter, paper and the departments' information) are read in your browser and sent only to Anthropic, under your own account's settings.
- **Staff names** for each department are sent to OpenAlex (`api.openalex.org`) to count their publications.

### With your Claude and Do it yourself

- Your materials go only to Claude, through your own Claude account and under that account's settings. There is no API key.
- Neither version sends anything to OpenAlex, and Do it yourself looks nothing up on the web.

### Analytics

The page tells a counter, GoatCounter, when it is opened, when a run finishes and when a file is downloaded, with the country and the time, and nothing else. It sets no cookie and keeps no address. Counting use shows that this free educational tool is being used.

- It runs on the website only. The chat version and the artifact carry no counter and report nothing.
- GoatCounter is open-source, privacy-first analytics: it sets no cookie, stores no address and needs no consent notice, so there is none. Its script loads from gc.zgo.at and the counts go to wellmatched.goatcounter.com.
- The three events it records are a run finishing, a download of the chat version from the With your Claude card, and the artifact being opened from the Do it yourself card. Nothing you type or upload is ever sent to it.

## For university IT and data protection teams

- **The tool itself keeps nothing.** There is no server, database or account, so a candidate's materials, key and results exist only in their own browser and, once sent, under their own Anthropic account's settings.
- **Materials go to the candidate's own provider.** A candidate's materials are sent to Anthropic under their own API key or Claude account, and that account's terms and settings apply.
- **Public staff information only.** When the website version looks up a department, it reads only the school's own public staff pages and notes professional facts: name, title, research, journals and the page's address.
- **Counting without cookies.** GoatCounter counts visits, runs and downloads by country and time, sets no cookie and keeps no address.
- **Fully auditable.** The complete source code, including every network call, is public in this repository.
- **Run it yourself.** Institutions can download the repository and serve it from their own servers.

## Third-party resources

- Anthropic's API (`api.anthropic.com`), for the reading, in the website version
- OpenAlex (`api.openalex.org`), for publication counts, in the website version
- Google Fonts (`fonts.googleapis.com`), for the typeface
- GoatCounter (`gc.zgo.at` and `wellmatched.goatcounter.com`), on the website only
- pdf.js 3.11.174 and mammoth.js 1.6.0, the PDF and Word readers, kept in `lib/` and loaded from this repository

## Repository security

The repository is the real security boundary: whoever can push to it changes what every future visitor loads. Current position: a single maintainer, with no write access granted to anyone else; two-factor authentication on the GitHub account [confirm]; branch protection on main [confirm in settings]; GitHub security features (Dependabot and code scanning) [confirm in settings]; and only the two libraries in `lib/` as dependencies.

## Keeping your key safe

Make a key just for this tool at [console.anthropic.com](https://console.anthropic.com), set a monthly spending limit on it, and delete it when you no longer need it. Never paste your key into a copy of the page from a source you do not trust.

## Text from websites

When the tool reads departments' web pages, it treats what it finds as information, never as instructions. A page cannot tell it to do anything.

## Reporting a problem

If you find a security or privacy problem, please email [ammon.salter@wbs.ac.uk](mailto:ammon.salter@wbs.ac.uk) rather than opening a public issue. Say what you found, how to repeat it and what harm it could do. You will get an acknowledgement within 7 days, and confirmed problems will be fixed promptly.

## What this file does not cover

- Problems in browsers, operating systems or third-party services (GitHub Pages, Anthropic, OpenAlex, Google)
- Problems arising from changes people make to their own copies of the code
- Errors in the tool's readings or advice (please report those as ordinary issues)
