# Narrow niches like Pilates: shortlist

Researched 2026-10-15 after Darren's feedback that finance is too broad and the first candidates looked like budgeting apps. Method: [early-adopter-niche-method.md](early-adopter-niche-method.md). Goal: a small, fast-growing group of people (like Pilates in 2023) where no app owns the generic search yet.

## How each niche was checked

- **Growth:** outside numbers (participation, prices, press). Google Trends could not be pulled: the Apify Trends scraper stalled twice (Google blocks it), so Trends still needs a manual look at trends.google.com.
- **App competition:** the top 10 US App Store results for the niche's generic search, with each app's rating count and launch date (iTunes Search API, fetched through Firecrawl). Few ratings across the top 10 = no brand owns it yet.

## The 13 niches at a glance

| Niche | Growing? | Top App Store results for the search | Verdict |
|---|---|---|---|
| **Small vending machine operators** | TikTok side hustle; a YouTube short at 58M views; 30K-member operator group in Australia alone | Biggest has 434 ratings; 4 launched Jul to Oct 2026 with 0 to 5 ratings. Real tools for small operators exist only as web software at $19 to $99/mo | **Pick #1** |
| **Silver and gold stacking** | Silver about $77/oz in Feb 2026 (record territory); 3 new trackers launched in 2026 | Dealers (APMEX, JM Bullion) own the search. Real stack trackers: 0 to 86 ratings, 3 launched in 2026. A dozen small web trackers, no leader | **Pick #2** |
| No-buy year / no-spend | WSJ: "No Buy January" searches at a 5-year high; 70K-member subreddit | 8 apps launched in 2026, all 0 to 42 ratings: lots of builders, no winner | Crowded with tiny apps, seasonal (January), and users are trying *not* to spend. Skip |
| Padel (US) | 1.07M US players in 2025, first year counted (SFIA); USPA membership +53.5% in 2025; about 1,000 courts | Playtomic (13.8K) owns booking. At least 7 score/stat apps for Apple Watch already (Start Padel, Padelistics, PadelWrist, PadelTracker...) | Fast-growing, but the obvious app is already built 7 times. Skip for now |
| Reseller profit tracking (Whatnot, eBay) | Whatnot has 1M+ ratings | 8 trackers launched in 2026 with 0 to 14 ratings; Flippd 148 | Same crowding pattern. Skip |
| Coast FIRE | Steady niche | 5 calculators, 1 to 3 ratings each | Calculators don't sell subscriptions. Skip |
| Cash stuffing | Peaked 2022 to 2023 | Fleur 13K, Goodbudget 13.5K, Budget Bestie 3.2K | Already has brands. Skip |
| Pokémon card value | Big | Collectr 68K, PSA 60K | Owned. Skip |
| Travel nurses, coin roll hunting, Pilates class tracking | Mixed | Job boards / coin ID scanners / studio apps own the searches | Not a fit for a tracker |

**Pattern worth knowing:** almost every niche that's growing fast now gets 5 to 10 tiny indie apps within months (AI-built apps flood the store). So "no app exists" is rare. The better opening is a niche where **nobody has more than a few hundred ratings** *and* the buyer has a real reason to pay. Small business owners pay; people trying to save money don't.

## Pick #1: Route app for small vending operators (1 to 25 machines)

**Who:** people who bought 1 to 25 used snack/drink machines as a side hustle, often after a TikTok video. Typical numbers from operator interviews: $100 to $500 sales per machine a month, 30 to 50% margin, location commissions of 6 to 30%, restocking from Costco or Sam's Club, a 3 to 4 hour weekly run.

**What they do today:** spreadsheets, notes, the card reader's own app (Nayax, Cantaloupe) for card sales, and memory for cash. Software built for them (Roundkeep $19/mo, VendSheet and VendorsReach $49/mo, VendBuddy $49/mo) is web-first and aimed at 5 to 150 machines. Roundkeep's founder built it because the alternatives "wanted me to become a 500-machine enterprise or left me stitching together spreadsheets".

**The app (phone-first, used standing at the machine):**
1. **Visit log:** tap a machine, enter the cash count and card total, tick the slots you refilled, snap a photo. 30 seconds per machine.
2. **Profit per machine:** sales minus product cost, commission and card fees, so you see which locations actually make money. Operators repeatedly say the location is everything, and most beginners can't tell a $90 site from a $400 one.
3. **Costco list:** from what sold since the last visit, it builds the shopping list for the next run.
4. **What sells where:** best and worst items per location, so you swap slow sellers.
5. **Tax pack:** miles driven, expenses and income per year, exported for Schedule C.
6. **Route value:** "what is my route worth?" for selling, and a checker for the many 1 to 5 machine routes listed on Facebook Marketplace.

**Why it isn't a budgeting app:** it's a small-business tool for a physical side hustle. Nothing in it touches a bank account.

**Money:** $9.99/mo or $79/yr. A beginner can't justify $49/mo web software for 3 machines, but $10 is easy if it shows one bad location.

**Risks:** the market is small (no count of US hobby operators exists); some beginners quit within a year; 4 brand-new competitors launched in the last 4 months, so speed and App Store search matter. Telemetry/card-reader imports are the hard part and can wait for version 2.

## Pick #2: Private stack tracker for silver and gold stackers

**Who:** people buying physical coins and bars, a group that grew with record silver prices (about $77/oz in Feb 2026) and Costco selling bullion. Identity-driven, like "Pilates girls": stackers, r/Silverbugs, "Silver Squeeze".

**What they do today:** spreadsheets (GOOGLEFINANCE breaks, per a 2026 tracker comparison), pen and paper for privacy, or dealer apps whose tracker is an afterthought. In the App Store the search is owned by dealers; actual trackers have under 100 ratings.

**The app:**
1. **Snap the invoice:** photograph the dealer receipt or email; the app reads product, weight, purity, price, shipping and tax, and adds it. No typing.
2. **Live melt value and real cost:** what the stack is worth at spot now, versus what you paid including premiums.
3. **Premium checker:** "this Silver Eagle costs 28% over spot, the average you paid is 19%". A shop and coin-show mode that works offline.
4. **Private by design:** data stays on the phone (iCloud only), no account. Stackers care about this a lot; MyOunces markets itself on it.
5. **Insurance and estate sheet:** a PDF inventory with photos for the insurer or family.
6. Price alerts and a home-screen widget.

**Why it isn't a budgeting app:** it's an inventory and valuation tool for a collecting hobby.

**Money:** stackers already pay for this: MyOunces $79 one-time, SilverOfTruth $69.99/yr, StackerScan $4.99/mo. A one-time unlock (about $39 to $59) fits the privacy crowd; a yearly plan for alerts.

**Risks:** interest rises and falls with the silver price; about a dozen small trackers exist on the web, so invoice scanning and privacy have to be the clear difference; finance category review is stricter (no buying/selling, just tracking, keeps it simple).

## Earlier candidates, revisited

The paycheck checker and pay-schedule planner from the first pass are finance utilities with a narrow job, not budgeting apps, but they sit in the broad personal-finance audience Darren wants to avoid. They are parked.

## Next steps (when Darren picks one)

1. Run the keyword collector on 10 to 15 search terms for the pick (e.g. "vending route", "vending tracker", "vending inventory" / "silver tracker", "stack tracker", "bullion tracker") to see ranks and rating growth over a couple of weeks.
2. Mine the 1-star reviews of the closest apps (pipeline step 3).
3. Read 10 small-creator videos in the niche ("vending route day in the life", "silver haul") with the transcript method to find the workarounds and the identity words for branding.
