# App categories for a solo indie portfolio

Researched 2026-10-15. Companion to the strategy doc ["App Development Strategy for a Solo Indie Portfolio"](https://claude.ai/code/artifact/c2453557-3c03-4e9a-90b9-46edfbd913d2), which covers validation, monetization mechanics and ASO; this file only compares categories.

Scores are 1 (low) to 5 (high). Revenue numbers are from Adapty's 2026 report (16,000 apps, $3B revenue) and RevenueCat's 2026 report (115,000 apps) unless marked. Crowding and build scores are my judgment from the sources plus general knowledge, not measured.

## Summary table

| Category | How it makes money | Money signal (2026 data) | Crowding | Build difficulty | Solo fit |
|---|---|---|---|---|---|
| Utilities (scanner, QR, converter, file tools) | Weekly sub with a short trial | 12-mo LTV $46.30; trial users $68.90; best first-renewal retention (58%) | 5 | 1-2 | Good, if you find an unowned keyword |
| Health & fitness (habit, fasting, water, workout, calorie) | Annual sub (61% of category revenue) | Highest install LTV ($1.20/install); best trial-to-paid (35%); worst first renewal (30%) | 5 | 2-3 | Good |
| Productivity (focus timer, to-do, notes niches) | Sub, direct purchase beats trial | Highest 12-mo LTV ($46.97); best 1-year retention (14%) | 5 | 2-3 (sync is the hard part) | Good for narrow niches |
| Education (flashcards, exam prep, language) | Annual sub with trial; heavy discounting | 12-mo LTV $45.10; 23% of trials start a month+ after install | 4 | 3 (content is the cost) | Medium |
| Finance (budget, expense, invoice, net worth) | Sub; some one-time | Not broken out in either report | 4 at the top (Monarch, YNAB, Copilot) | 4 with bank sync, 2 without | Medium; manual-entry or B2B tools (invoices) fit better |
| AI wrappers / Photo & video AI | Weekly sub, high price | +41% revenue per payer, but 21% annual retention vs 31% for non-AI; highest trial refunds (6.4%) | 5 and easy to copy | 1-2 to build, API cost per user | Risky: fast money, fast churn, thin moat |
| Lifestyle / wellness (journal, mood, meditation, sleep) | Moving to one-time purchases (26% of revenue) | Top 10% of apps take 98% of category revenue; trials cut LTV 21% | 5 | 2 (content-heavy for meditation/sleep) | Poor unless very niche |
| Niche vertical tools (plant ID, baby tracker, period tracker, trade-specific tools) | Sub or one-time | Not measured as a group | 2-3 | 2-3 | Best odds: lower competition, clear buyer |
| Games (puzzle, hybrid-casual) | Rewarded ads + "remove ads" + IAP | Puzzle revenue +21% YoY in Q1 2026; ad-only hyper-casual no longer pays back install costs | 5 (largest category, ~12-18% of all apps) | 4 (art, tuning, live ops) | Poor as a first bet; relies on paid installs, not search |
| Social / marketplaces | Ads, fees | n/a | n/a | 5 (needs both sides of a network) | Skip |

## Notes by category

**Utilities.** Easiest to build and retains best once it solves the problem, and trials work as a quality filter. The catch is that head keywords ("pdf scanner", "qr code scanner") are saturated and Apple keeps building utilities into iOS (WWDC 2025 absorbed call screening, flight tracking and local recording). Look for long-tail jobs Apple won't do.

**Health & fitness.** Users commit fast and quit fast, which is why annual plans dominate: they lock in revenue before motivation fades. Widgets, HealthKit and Live Activities can lift retention and push toward native Swift.

**Productivity.** Highest value per payer and best retention, but generic to-do and notes apps are a graveyard. Direct purchase beats trials here, so a hard paywall fits.

**Education.** Users evaluate slowly, so re-engagement matters more than the first-session paywall. Kids apps add Apple Kids Category and COPPA rules (not researched here; check before building).

**Finance.** Bank sync (Plaid) adds per-connection cost, security review and support load; manual-entry apps avoid that. Darren's tradeapp is a private net-worth tracker, so this category has some reusable code but the public market is led by funded apps.

**AI wrappers.** RevenueCat: AI apps monetize better early but churn about 30% faster and refund more. Apps launched in 2025 or later earn only 3% of subscription revenue. Treat AI as a feature inside another category, not the category.

**Lifestyle.** The most winner-take-all category in Adapty's data. Users increasingly want to buy, not subscribe.

**Games.** Puzzle is the bright spot, but discovery depends on paid user acquisition and creative testing, which costs money a solo dev usually lacks.

## How this ties to the keyword collector

`darrenzou/app-keyword-tracker` already tracks keywords across most of these rows (habit tracker, budget planner, meditation, focus timer, flashcards, pdf scanner, plant identifier, baby tracker and more). Once it has a few weeks of data, rank the rows above by that data instead of by these judgment scores.

## Where the evidence is weak

- Category revenue numbers come from subscription-tool vendors' own customers, which skews toward apps that already monetize.
- Finance, games and niche tools have no comparable per-category subscription benchmarks here.
- Crowding scores are judgment, not counts. Appfigures and Statista per-category app counts are paywalled.

## Sources

- [Adapty, State of In-App Subscriptions 2026](https://adapty.io/state-of-in-app-subscriptions/) and [key findings](https://adapty.io/blog/mobile-app-monetization-2026/), [trial vs direct by category](https://adapty.io/blog/free-trial-vs-direct-purchase-subscription-apps/)
- [RevenueCat, State of Subscription Apps 2026](https://www.revenuecat.com/state-of-subscription-apps)
- [TechCrunch, AI apps struggle with long-term retention (Mar 2026)](https://techcrunch.com/2026/03/10/ai-powered-apps-struggle-with-long-term-retention-new-report-shows)
- [PPC Land, AI apps earn 41% more per user but churn 30% faster](https://ppc.land/ai-apps-earn-41-more-per-user-but-churn-30-faster-revenuecat-finds/)
- [Cinevva, Casual games trends 2026](https://app.cinevva.com/guides/casual-games-trends-2026)
- [BusinessStats, App Store apps by category 2026](https://businesstats.com/apple-app-store-number-of-available-apps-by-category/) and [42matters iOS stats](https://audience.42matters.com/ios-apple-app-store-statistics-and-trends)
- [TechCrunch, what Apple sherlocked at WWDC 2025](https://techcrunch.com/2025/06/10/wwdc-2025-everything-that-apple-sherlocked-this-time/)
- [Plaid pricing on Capterra](https://www.capterra.com/p/174384/Plaid/pricing/)

## Deep dive: GRE and CFA study apps (2026-10-15)

| | GRE | CFA |
|---|---|---|
| Test takers | Under 200,000 in 2024-25, down from 350,000+ in 2020-21 ([Poets&Quants](https://poetsandquants.com/2026/02/04/ets-mulls-selling-its-crown-jewels-gre-and-toefl-could-be-worth-500m/)) | Level I alone: 24,000 to 31,500 per sitting, five sittings Aug 2025 to Aug 2026 ([CFA Institute](https://www.cfainstitute.org/about/press-room/2026/cfa-institute-reports-results-cfa-program-level-i-testing-august-2026)); Levels II and III on top |
| Leaders | Magoosh (about $149-179 for 6 months; free vocab app with ~12,000 ratings at 4.8), GregMat ($7.99/month), Manhattan Prep, Kaplan, Target Test Prep | Kaplan Schweser, UWorld, AnalystPrep, plus the free official CFA Learning App; providers charge roughly $300 to $1,000+ |
| Crowding | High, with a cheap price anchor and a free category leader | Medium: incumbents are web-first with a mobile companion |
| Build difficulty | Low-medium; vocab content is easy, quant and verbal questions are work | High on content: you can't use CFA Institute's curriculum (only approved prep providers may), so every question must be original and correct |
| Verdict | Shrinking market, crowded at the top. Skip unless a very narrow angle | Better of the two: smaller but paying, mobile-first gap. Content accuracy is the main cost and risk |

Legal note: CFA Institute forbids its logo for all prep providers and only enrolled providers may say "CFA Institute Prep Provider" ([CFA Institute](https://www.cfainstitute.org/programs/cfa/prep-providers)). An app using "CFA" in its name likely needs a non-affiliation disclaimer; whether the bare name is allowed is unconfirmed. GRE is an ETS trademark with similar care needed.

Sources: [Katalyst GRE prep comparison](https://katalystprep.com/gre/guides/best-prep-courses/), [UWorld CFA question bank comparison](https://finance.uworld.com/cfa/best-cfa-question-bank/) (vendor page), [Magoosh vocab app on AppGoblin](https://appgoblin.info/apps/672962658).

## Credential exam niches compared (2026-10-15)

The biggest finding: generalist prep-app portfolios already cover almost every exam. Pocket Prep sells per-vertical apps (Nursing $20.99/month or $124.99/year, Medical and EMS $15.99/month or $95.99/year) ([App Store](https://apps.apple.com/us/app/-/id1501741725)), and Higher Learning Technologies runs "Mastery" apps per exam (NCLEX RN Mastery about $25/month, $115/year) ([App Store](https://apps.apple.com/US/app/id625614526)). So every niche has at least one app competitor; the question is whether it has a deep, well-reviewed one. Their model (one app engine, a content pack per exam) is also the obvious portfolio play here.

"Takers" are yearly test takers. Estimates marked *est.*; prices and crowding marked *judgment* are from general knowledge, not checked this session.

| Exam | Takers per year | What people pay for prep | Crowding | Content difficulty | Verdict |
|---|---|---|---|---|---|
| CFA Level I | ~110,000 (24,000-31,500 per sitting, ~4 sittings) | $300-1,000+ | Medium; incumbents web-first | High; no official curriculum allowed | **Good** |
| CPA (4 sections) | 87,660 candidates in 2025, up from 74,165 ([NASBA](https://nasba.org/blog/2026/08/14/2025-nasba-report-now-available/)) | ~$1,000-3,500 for full courses (*judgment*: Becker, UWorld, Gleim) | High | High | Medium: big and growing, but four big content sets |
| NCLEX-RN / PN | RN ~330,000 *est.* (83,428 in Q1 2025 alone, [NCSBN](https://ncsbn.org/public-files/NCLEX_Stats_2025_Q1_PassRates.pdf)); PN 54,818 first-time US-educated | UWorld ~$349-399; apps $20-25/month | Very high | High; Next Gen case questions, clinical accuracy | Poor for a newcomer |
| USMLE Step 1 | ~55,500 (29,870 US + 25,660 non-US, [USMLE](https://www.usmle.org/performance-data)) | UWorld dominant; free Anki decks (*judgment*) | Very high | Very high | Skip |
| LSAT | 173,094 in 2024-25, rising ~6% ([LSAC](https://www.lsac.org/podcast/keeping-data-july-2026)) | LSAC's own LawHub plus courses (*judgment*) | High | High; real questions are licensed | Poor |
| GRE | <200,000, shrinking | GregMat $7.99/month; Magoosh free vocab app | High | Medium | Skip |
| CompTIA Security+ | Not found; 500,000+ certified by 2019, the US DoD baseline cert ([CompTIA](https://production-central-www.comptia.org/newsroom/comptia-security-surpasses-500-000-certified-milestone)) | Dion practice app $29.99; Professor Messer free | High, low price anchor | Medium; refreshed every ~3 years | Poor-medium |
| PMP | Not found | Cheap Udemy courses dominate (*judgment*) | High | Medium | Poor-medium |
| Real estate salesperson (per state) | No national count; California alone ~47,500 exams in FY2022-23 ([US Realty Training](https://www.usrealtytraining.com/blogs/california-real-estate-exam)) | Often bundled with required pre-license courses | Medium; state law sections are fragmented | Medium; 50 sets of state rules | **Good**: start with 2-3 big states |
| Trade and vocational (CDL, EPA 608, FAA Part 107 drone, electrician journeyman, insurance license) | Not found | Low to moderate | Low-medium (Pocket Prep has Part 107) | Low-medium; public handbooks and codes | **Good** for cheap, fast content packs |
| Actuarial (SOA Exam P, FM) | Not found | High (*judgment*) | Low-medium | Very high math | Niche: only with actuarial expertise |

**Pattern.** Medical and law exams are deep, expensive to write for, and owned by UWorld-style leaders. Huge IT exams have free or $30 anchors. The openings are where buyers pay real money but content is mobile-poor (CFA), or where the market is split by state or trade so national players don't go deep (real estate, trade licenses).

Sources: as linked inline, plus [GoodNurse NCLEX app comparison](https://goodnurse.com/article/264/best-nclex-prep-apps-2026-honest-comparison-for-ngn-adaptive-questions-value), [Dion Security+ bundle](https://diontraining.com/products/comptia-security-exam-voucher-usd-practice-exams-bundle), [Pocket Prep Medical](https://apps.apple.com/app/id1476171010).

## How trade and actuarial prep apps would work (2026-10-15)

**Shared engine.** One app codebase with a question bank, spaced repetition, timed practice exams that match the real format, and a readiness score. Each exam is a content pack. Free daily question quota, then a paywall. This is the model Pocket Prep and the "Mastery" apps run.

**Content workflow.** Draft questions with AI from public official sources, store the source paragraph with each question, and check every answer before shipping (by citation for trade exams, by computing the answer in code for actuarial math). Wrong answers are what sink reviews in this category.

### Trade and vocational

| Exam | Demand | Content source | Competition | Fit |
|---|---|---|---|---|
| FAA Part 107 (drone) | 493,000 certified remote pilots by Dec 2025, up 70,000+ in one year ([Commercial UAV News](https://www.commercialuavnews.com/ten-years-of-part-107-the-regulation-that-created-the-u-s-drone-industry)) | FAA's test standards and testing supplement are public US government documents. 60 questions, 70% to pass | Pocket Prep, Kaplan, drone schools | **Best first pick**: public content, steady demand, one national exam |
| EPA 608 (HVAC refrigerant) | Not found; required for every HVAC tech handling refrigerant | EPA rules are public | Not checked | Good second pick; verify competition first |
| Journeyman electrician | State-by-state | Exams are open-book on the NEC; the NEC is NFPA-copyrighted, so cite article numbers, never reproduce code text | iContractor, open-exam-prep.com already do state pages | Medium: deep content, 50 variants |
| CDL permit | Large | State CDL manuals | Flooded with near-identical "CDL Practice Test 2026" apps ([example](https://apps.apple.com/us/app/id6499304043)) | Skip |

Trade buyers spend less than finance candidates: expect a weekly or lifetime unlock (CDL apps sell lifetime around $99.99) rather than $300 courses.

### Actuarial (SOA Exam P, then FM)

- **Demand:** Exam P had 13,182 sittings across six windows in 2025, up 51% from 2022 ([actuary.info](https://actuary.info/insights/exam-p-volume-surge-mas-i-entry-funnel)). Exam fee $270 ([SOA](https://www.soa.org/education/exam-req/syllabus-study-materials/exam-and-module-fees)). Pass rate about 44-46%.
- **Competition:** Coaching Actuaries charges $195 (practice only) to $600 (full course) per exam for 180 days ([pricing](https://coachingactuaries.com/exam-p/pricing)); FreeFellow offers 1,100+ free Exam P questions. No dedicated mobile-first app turned up.
- **Content:** Probability and financial math. Every answer can be checked by computing or simulating it, which makes AI-drafted questions safer here than in most exams.
- **Ceiling:** Small. Even 5% of Exam P sitters paying $100 is about $66,000 a year. Adding FM and later exams raises it.
- **Fit:** Good as a high-price, low-volume pack if you're comfortable checking probability problems; a phone-first drill app beside Coaching Actuaries' desktop course is the gap.

## Part 107 and Exam P: monetization and revenue estimates (2026-10-15)

**Model.** Yearly revenue = test takers × share who install your app × share of installs who pay × price per payer, minus Apple's 15% (Small Business Program). The install share and conversion rates are my assumptions: no published install-to-paid benchmark exists for test-prep apps, and exam buyers are higher-intent than the 2-3% median subscription app.

| | Test takers/yr | Installs (share) | Payers (conversion) | Price per payer | Net per year |
|---|---|---|---|---|---|
| Part 107, low | 73,914 | 2,200 (3%) | 89 (4%) | $25 | ~$1,900 |
| Part 107, mid | 73,914 | 7,400 (10%) | 590 (8%) | $30 | ~$15,000 |
| Part 107, high | 73,914 | 18,500 (25%) | 2,200 (12%) | $40 | ~$75,000 |
| Exam P, low | 13,182 | 660 (5%) | 33 (5%) | $40 | ~$1,100 |
| Exam P, mid | 13,182 | 2,000 (15%) | 200 (10%) | $60 | ~$10,000 |
| Exam P, high | 13,182 | 4,000 (30%) | 590 (15%) | $90 | ~$45,000 |

Part 107 takers: 73,914 in 2025 (67,576 in 2024), pass rate 83%, per a secondary source citing the FAA's annual test statistics ([Drone U](https://www.thedroneu.com/?p=43711)). Exam P: 13,182 sittings in 2025, including retakes ([actuary.info](https://actuary.info/insights/exam-p-volume-surge-mas-i-entry-funnel)).

"High" needs a top-3 App Store ranking for the exam's main keywords. The strategy doc's base rate (median subscription app under $50/month after a year) says low-to-mid is the realistic expectation for a first launch.

**Part 107: how hard to monetize.** Medium-hard. Much is free (the FAA's own study guide and testing supplement, YouTube courses), and paid courses with pass guarantees cost $147-299 (Drone U $147, Pilot Institute ~$149-179, Drone Pilot Ground School $299) ([Drone Girl](https://www.thedronegirl.com/2025/11/12/best-part-107-test-prep-courses-money-back-guarantee/)). App competitors include Rotate Pilot ($14.99/month) and Remote Pilot Ground School. Positioning: cheaper than a course, more realistic than free tests (practice with the real testing-supplement charts). Users leave once they pass, so sell an exam pass (about $25-40 one-time, or a 30-60 day pass), not an ongoing subscription.

**Exam P: how hard to monetize.** Easier per user, harder on volume. Candidates already pay $270 for the exam and $195-600 for Coaching Actuaries, and many employers reimburse study materials (inferred, not checked). FreeFellow's free question bank caps the low end. Price around $60-90 per exam window. Volume is the limit: 13,000 sittings a year, so the ceiling only rises by adding FM and later exams.

**Costs.** Apple developer fee $99/year; RevenueCat is free under $2,500 monthly revenue; AI drafting is cheap. The real cost is question writing and checking time: roughly 500-800 Part 107 questions and 400-600 Exam P questions with worked solutions.

## Game niches: App Store competition scan (2026-10-15)

Measured by running the keyword collector (`darrenzou/app-keyword-tracker`, branch `claude/project-thread-pospig`, data in `data/2026-10-15/`) on 32 game keywords. "Big" = 50,000+ App Store ratings. This measures competition, not demand: a second snapshot is needed for download estimates.

| Keyword | Big apps in top 10 | Median ratings, top 10 | Read |
|---|---|---|---|
| shogi | 1 | 104 | Empty but tiny audience in the US |
| interactive fiction | 0 | 130 | Empty; content-heavy |
| kakuro | 0 | 179 | Leaders are 2011-2019 apps with 300-2,600 ratings |
| go game | 0 | 210 | Small, dedicated, pays (SmartGo One) |
| chess puzzles | 1 (Chess.com) | 900 | **Niche apps are small (37-3,700 ratings); apps from 2024-25 rank top 6** |
| text adventure | 0 | 1,385 | AI Dungeon is the one bigger player |
| deckbuilder | 0 | 2,140 | Players pay upfront (Dawncaster $4.99) |
| minesweeper | 1 | 3,626 | Apple suggests "minesweeper no ads" |
| pinball | 0 | 3,801 | Licensed tables dominate |
| bridge card game | 0 | 4,051 | Older, paying audience; bidding AI is hard |
| nonogram, cryptogram, cribbage, euchre | 2-3 | 8,000-11,000 | Mid; one or two leaders each |
| sudoku, solitaire, mahjong, crossword, jigsaw, word game, spades, dominoes | 6-9 | 69,000-456,000 | Saturated |

No-ads signal: Apple's own search suggestions include "minesweeper no ads" and "euchre free no ads", so players in classic logic and card games search specifically for ad-free versions.

**Best fit without ads: a chess puzzle / tactics trainer.** Low competition among dedicated puzzle apps, an audience that already pays (Chess.com's paid tiers), small build (puzzles come from Lichess's openly licensed puzzle database, CC0, not checked this session), and monetization by subscription or one-time unlock. Runner-up: a premium roguelike deckbuilder (players pay $5-10 upfront) if you're willing to take on game design and balancing.
