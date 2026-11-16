# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

A single-page web app (`triage-desk/app.html`, published as a claude.ai artifact; `triage-desk/index.html` is the standalone copy). Designed phone-first: bottom tab bar on phones, side rail on wide screens.

## Users

One primary user: a digital transformation project coordinator. Colleagues across the organisation constantly ask for changes (new tools, automations, reports, process fixes) through intake forms and spreadsheets. The coordinator's job is to decide what gets done first, defend that order, and fit the work around a calendar full of Teams meetings, while keeping some time for themselves.

Not yet confirmed: whether a manager, requesters or a wider team will ever see the tool or its output. Treat it as a personal tool until told otherwise.

## Product Purpose

Turn a pile of change requests into a clear, defensible order and a realistic week.

- Import the exports from Microsoft Forms, Google Forms or a tracker (.xlsx, .xls, .csv) and score every request automatically.
- Group requests into four bands in the user's own words: Urgent, Priority, Later, Backlog.
- Spread the work across the coming weeks: high-priority work first, lower-priority work still moving, nothing scheduled over meetings or the user's protected time.

Success: the user opens it, sees at a glance how many requests sit in each band and what to do next, and gets time back for themselves instead of firefighting.

## Positioning

A personal triage desk, not a team project-management tool. Its mechanism is the combination of a transparent score the user controls (every rank can be explained factor by factor) and a planner that knows the user's real calendar and protects their own time. Generic trackers rank by whoever shouts loudest; this ranks by the user's own rules and plans around their actual day.

## Operating Context

- Requests arrive through forms and spreadsheets the user does not control; column names and answer formats vary (text like "High" or "Whole organisation", t-shirt sizes, hours, dates in UK day-first format).
- The user works in Microsoft 365. Teams meetings live in their Outlook calendar and come in as an exported .ics file (no live connector is set up yet).
- The user checks the app on a phone as well as a computer; the phone experience matters.
- UK context: British English, UK dates.

## Capabilities and Constraints

Confirmed and built:
- Scoring from business impact, urgency (or nearness of the delivery date), people affected, strategic fit, risk if not done, and ease; regulatory or mandatory requests get a boost. Weights and band thresholds are editable.
- Missing answers count as middle values and are flagged "Needs info" with who to ask.
- Statuses: New, Accepted, In progress, On hold, Done, Declined. The user can force a request into a band.
- Weekly plan: per-day capacity, working hours, a protected "Your time" block, a high/low priority split, longest stretch on one request, meetings and out-of-office days from the calendar, warnings when work will miss its date or a meeting overlaps protected time.
- Overview (home): this week's focus ring (average progress of the top focus items), active priorities, items this week, at risk, due in 30 days, delivery areas by team (filter the roadmap), a Now / Next / Later roadmap by delivery date with progress, a mini week calendar, and the week's focus items with mark-done.
- Each request has a progress percentage the user sets; Done means 100%.
- Data is private to the user (artifact database under the user's own path; browser storage in the standalone copy). CSV export of the ranked list and a downloadable intake-form template.

Technical constraints:
- One HTML file; external scripts only from approved CDNs (SheetJS for spreadsheets); fonts from Google Fonts (Material Symbols Rounded icons, Inter fallback).
- Network access from the build environment is restricted; impeccable.style and Microsoft APIs are not reachable from it.

Undecided:
- Who else sees the tool or its output (manager, requesters, team).
- Organisation type and therefore any mandatory accessibility standard or data-handling rules.
- Whether the scoring must follow an existing governance framework (a Change Advisory Board, RICE, MoSCoW, WSJF, a risk matrix) or stays the user's own.
- A live Outlook/Teams connection instead of .ics import.

## Brand Commitments

- Name in the app: "Digital Priorities Command Centre" (the user's reference design). The underlying project is Triage Desk.
- Band names are fixed in the user's words: Urgent, Priority, Later, Backlog.
- Navigation: Overview (home), My week, Priorities, Settings.
- Look: the user supplied a reference design (dark navy "command centre" dashboard with frosted glass panels, light cards for work items, an electric-blue accent, a ring gauge for this week's focus, a stats strip, delivery areas, a Now / Next / Later priority roadmap, a mini week calendar and a "This week's focus" bar). Treat that reference as binding; it replaces the earlier "clean blue" palette.
- The reference carried the user's employer name and logo and a bridge photograph. Do not put a real organisation's name or logo into a published page, and do not fabricate a photograph; the user may add their own name and photo to their own copy.
- Voice: plain, direct British English. Controls say what they do.

## Evidence on Hand

- No real requests, requester names, meetings or organisational data are in the repository. Everything shown in the app is labelled example data (fictional requesters, an example Change Advisory Board meeting).
- No logos, testimonials, metrics or case studies exist. Do not fabricate any.

## Product Principles

1. The user's time comes first: protected time is never scheduled over, and the plan says plainly when there is no room left.
2. Every rank is explainable: show why a request scored what it did, in the factors' own terms.
3. Fit real inputs: accept messy form exports and calendars as they come; let the user correct the mapping instead of demanding a format.
4. Decide, don't just display: the home screen asks for a decision (accept, hold, done) rather than showing more charts.
5. Personal and private by default: nothing is shared or sent anywhere unless the user chooses to.

## Accessibility & Inclusion

No mandated standard confirmed yet. Built to WCAG 2.2 AA as a working baseline: readable contrast in light and dark modes, visible keyboard focus, touch targets around 44px, reduced-motion support. If the organisation turns out to be UK public sector, AA becomes a legal requirement.
