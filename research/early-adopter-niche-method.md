# Early-adopter niche method for apps

Adapted 2026-10-15 from Seena Rez, ["how I built a $2.7M brand using a.i"](https://www.youtube.com/watch?v=5FokzkHTpc0) (Pilates grip socks), for Darren's app portfolio. Companion to [trend-to-app-pipeline.md](trend-to-app-pipeline.md). Narrow-niche shortlist from the second pass: [narrow-niche-shortlist.md](narrow-niche-shortlist.md). This method is a second scouting source that finds needs *before* they show up on the top charts.

## The video's method in one paragraph

Enter a growing market (Pilates: rising on Google Trends, 11.5% CAGR). Search YouTube for the niche's own micro-influencer formats ("day in the life of Pilates", routine, vlog). Paste the transcripts into an AI and ask for the "early adopter products" mentioned. Check each in Google Trends for a recent, steep rise. Listen to how people talk about it: "those grippy socks" means they want the product but no brand owns it yet ("product validation without brand saturation"). Build the brand around the buyers' identity ("that girl"), copying the look of a non-competing brand that serves the same identity (Glossier). Then distribute with stitched short videos and retarget the viewers.

## The same steps for apps

| # | Video step | App version | Free tool |
|---|---|---|---|
| 1 | Growing market: Google Trends up year on year, CAGR around 10%+ | Pick a growing **lifestyle niche** first (Pilates, cozy gaming, cash stuffing, moving abroad, digital detox), not an App Store category. Confirm with app-side growth: rating counts of the niche's top apps rising week to week | Google Trends; our keyword collector (rating velocity). CAGR only as a tiebreaker, see below |
| 2 | "Day in the life of [niche]" videos from micro-influencers | Formats where creators name apps in passing: "what's on my iPhone", "my phone setup", "[niche] routine", "budget with me", "paycheck routine", "games I'm playing this month", "day in the life [niche]". Prefer small creators and videos from the last 6 months | YouTube search (yt-dlp search works from GitHub Actions) |
| 3 | AI lists the early-adopter products in each transcript | Claude lists (a) small or new apps mentioned, (b) **workarounds**: Notes, spreadsheets, Notion templates, Shortcuts, multi-app chains, "I wish there was", (c) questions the creator asks the audience | Firecrawl scrape returns the full transcript from the cloud (about 1 credit a video); YouTube blocks our own runners. Video descriptions often list every app with its App Store link |
| 4 | Google Trends: recently emerged and growing fast | Google Trends for the concept term; App Store: is the small app under a year old and gaining ratings fast? | Google Trends; collector |
| 5 | "Product aware, not brand aware" | People describe the job, not a brand ("a focus timer that's like a flight", "a widget pet"). In the store: the generic keyword's top 10 results have few ratings, so no one owns it yet | Collector: top-10 rating counts per keyword |
| 6 | Identity branding ("that girl", copy Glossier's look) | Find the identity in creator titles ("that girl", "budget girlies", "cozy gamer", "pink Pilates princess", FIRE) and borrow the visual language of a non-competing brand that serves it. This is also what keeps us clear of Apple's copycat rules (4.1, 4.3): same job, different and better product | Creator video titles; Pinterest |
| 7 | Stitch a viral niche clip, reveal the X factor in the first 3 seconds, retarget viewers | Short demo videos of the app on TikTok/Reels in the niche's language; paid retargeting of video viewers later | Organic is free; retargeting is paid |

### Which videos to use

The test below confirmed the video's warning against "trending product" lists. "Best budgeting apps of 2026" and "10 cozy iPad games" videos only name the brands that already won (Monarch, YNAB, Copilot, Stardew Valley, Plants vs. Zombies): that's the late majority. Routine and setup videos from small creators are where the early adopters are.

### On CAGR

Market-report CAGRs for apps are too inconsistent to filter on. For the same years, personal finance apps are quoted at **$9.95B growing 11.65%** ([Future Market Report](https://www.futuremarketreport.com/industry-report/personal-finance-app-market)) and **$207.5B growing 25%** ([Persistence](https://www.persistencemarketresearch.com/market-research/personal-finance-app-market.asp)); focus timer apps at 7.8% ([Market Intelo](https://marketintelo.com/report/focus-timer-app-market)) and 13.7% ([Growth Market Reports](https://growthmarketreports.com/report/focus-timer-app-market)). Use a CAGR only to ask "is this double digit?", and lean on Google Trends plus our own rating-velocity data.

| Niche | Quoted CAGR | Source |
|---|---|---|
| Cozy gaming | 12.5% ($1.9B in 2025) | [HTF](https://www.htfmarketinsights.com/report/4382814-cozy-gaming-market) |
| Mobile puzzle games | 8.5% to 10.5%; 2024 downloads +10%, revenue +49% | [Dataintelo](https://dataintelo.com/report/global-mobile-puzzle-game-puz-market), [InvestGame](https://investgame.net/news/pdf/casual-mobile-games-a-marketing-and-monetization-report/) |
| Brain-training puzzle games | 9.8% (fastest puzzle sub-genre) | Dataintelo |
| Budgeting apps | 9.5% to 13.4% | [DataHorizzon](https://datahorizzonresearch.com/budgeting-apps-market-47078), [Growth Market Reports](https://growthmarketreports.com/report/budgeting-app-market) |
| Digital detox apps | 11.95% | [Research and Markets](https://www.researchandmarkets.com/reports/6122120/digital-detox-apps-market-global-forecast) |

## First test run (2026-10-15, 5 transcripts)

### Utility

**"I set up my iPhone to cure my doomscrolling"** ([Tommyisme](https://www.youtube.com/watch?v=AGXcO2Axkys), Aug 2026, 20K views). Small apps he uses: FocusFlight (a Pomodoro timer framed as a flight: pick a seat, tear the boarding pass, plane noise, lock-screen widget), Pixel Pals (widget pet), Hands Time (Nothing-style clock widgets), Anytype, and LockTerm, a terminal-style Live Activity he built himself and wants to add "a dynamic pet" to. The cluster: lock-screen widgets and Live Activities, gamified focus, pets, all sold as anti-doomscrolling.
- **Candidate: a lock-screen focus pet.** A Live Activity companion that reacts to focus sessions and screen time, joining three things he uses separately.

**"What's on my iPhone fall 2026"** ([Natalie Cange](https://www.youtube.com/watch?v=nWTVuir1kCc), Sep 2026, 4.8K views). Workaround each season: find images on Pinterest, download, import into Widgetsmith, name, add widget.
- Possible candidate: seasonal aesthetic widget sets. Caution: wallpapers are on Apple's saturated list, so it would need to do more than show images.

### Finance

**"Do This EVERY Time You Get Paid"** ([Rashida Herbers](https://www.youtube.com/watch?v=4RVf2N_9nw4), Aug 2026, 535K views). Step 1 is "verify your paycheck": write base pay, taxes and every deduction in your phone notes and compare each new stub. She lost 4 months of 401(k) contributions to a payroll error that hit her whole department. A Notes workaround with no product behind it. She also names "complexity paralysis": people download budgeting apps and abandon them.
- **Candidate: paycheck checker.** Photograph the pay stub; the app compares it with the last one, flags changed deductions, missing retirement contributions and raise math, and drafts the note to HR. No bank sync, so it's a small build.

**"$4003.68 Paycheck Budget | $600k Debt Payoff Journey"** ([Wicked Stepmom Budgets](https://www.youtube.com/watch?v=H8LGi5tTlPE), Oct 2026, 182 views: a true micro-creator). Uses YNAB, and asks her audience how to budget a twice-monthly paycheck against every-other-week transfers, plus irregular commissions. Also tracks a tenant who stopped paying rent.
- **Candidate: pay-schedule planner.** Tells you what to fund from each paycheck when pay dates, bill dates and transfers run on different cycles. Second idea: a rent tracker for small landlords.

### Games

**"10 Cozy iPad Games You'll LOVE"** ([Flourish Planner](https://www.youtube.com/watch?v=u4OgWr6aDTk), Feb 2025, 145K views). Every title is mainstream (Stardew Valley, NYT Games, Hello Kitty Island Adventure). The one lead: Tsuki's Odyssey's "check in and see what happened" slow-life loop. The next games run should use "cozy games I'm playing this month", "day in the life cozy gamer" and small streamers.

## Next steps for the candidates

1. Google Trends for "paycheck errors / check pay stub", "biweekly budget", "focus timer widget pet".
2. Run the keyword collector on each candidate's generic keywords to see whether the top 10 results are small (product aware, not brand aware).
3. Mine 1-star reviews of the closest existing apps (pipeline step 3).
4. Repeat steps 2 and 3 above on 10 to 20 more videos per category before choosing a build.
