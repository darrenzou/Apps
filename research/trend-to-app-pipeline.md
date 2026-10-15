# Trend-to-app pipeline: recommendations

Researched 2026-10-15 for Darren's idea: a daily Claude automation that spots rising App Store trends, builds an improved version of the leading app, and submits it the same day.

## Verdict

Every step can be automated cheaply except two, and those two decide whether the plan works:

1. **"Copy the top app with small tweaks" is what Apple rejects and bans for.** Guideline 4.1(a): "Don't simply copy the latest popular app on the App Store, or make some minor changes to another app's name or UI." Guideline 4.3(b) (tightened June 2026): no apps "indistinguishable from what's already widely available... Repeated submissions of this kind may lead to removal from the Apple Developer Program." Apple's forum post on copycats: "accounts that repeatedly submit copycat apps... will be closed." Removal takes down every app on the account, not just the copy. ([guidelines](https://developer.apple.com/app-store/review/guidelines/), [Apple forum](https://developer.apple.com/forums/thread/782175), [9to5Mac, June 2026](https://9to5mac.com/2026/06/09/apple-tightens-app-review-guidelines-against-apps-that-do-not-add-value-to-the-app-store/))
2. **"Built and submitted within the day" works; "live within the day" doesn't.** Apple says 90% of submissions are reviewed within 48 hours (average 1.5 days); developers reported 7 to 30+ day waits during the spring 2026 submission surge. ([The Next Web](https://thenextweb.com/news/vibe-coding-apple-app-store-surge-crackdown))

So the version that works: **scout daily, build a candidate daily if one qualifies, but submit at most 1 to 2 new apps a week, each with a real difference, after you approve it.** Aim the automation at "same job, better product" (fix what the leader's 1-star reviews complain about, new name, own design), not "copy".

## The pipeline

| Step | What it does | Free option (recommended) | Industry standard |
|---|---|---|---|
| 1. Scout trends | Daily snapshot of top charts and keyword results; flag apps whose ratings grow fast, new apps (<90 days) climbing, and keywords with small leaders | Our keyword collector (GitHub Actions, free) plus Apple's free top-charts feeds: `rss.marketingtools.apple.com/api/v2/us/apps/top-free/100/apps.json` and the legacy `itunes.apple.com/us/rss/topgrossingapplications/limit=100/json` | Sensor Tower (median ~$75,000/yr, quote only; now also owns AppMagic and data.ai). Appfigures market data from $599.99/mo |
| 2. Size the niche | Downloads proxy and revenue proxy for the leader | Rating-count growth × ~70 = downloads (the collector already does this); grossing-chart presence = revenue | Appaloma $59/mo (4,000 niches with revenue, paywalls and pooled 1-star reviews: closest to what you want); AppMagic free tier |
| 3. Find the improvement | Pull the leader's recent reviews and have Claude cluster the complaints into a feature list | Apple's free customer-reviews feed: `itunes.apple.com/us/rss/customerreviews/page=1/id=<APP_ID>/sortby=mostrecent/json` (up to ~500 reviews) | Appaloma, AppFollow ($179/mo) |
| 4. Build | Claude writes the app from one shared Expo (React Native) starter with RevenueCat paywall, onboarding and settings pre-wired | Claude Code (you already have it) + Expo. Builds: EAS free plan 15 iOS builds/mo; GitHub Actions macOS free on a public repo (~200 min/mo private); Codemagic 500 free min/mo; Xcode Cloud 25 h/mo with the Apple membership | AI app builders Rork, Vibecode, a0.dev ($20/mo each); not needed since Claude does the coding |
| 5. Test | Install on your phone before anything goes to Apple | TestFlight (free) | — |
| 6. Submit | Upload build, metadata, screenshots, submit for review | fastlane `deliver --submit_for_review` with an App Store Connect API key (free) | — |
| 7. Track | Keywords and rankings once live | Collector again; Astro $9/mo if you want more | AppTweak €79+/mo |

Fixed cost: the Apple Developer Program at $99/year. Everything else above can stay at $0; Astro ($9/mo) or Appaloma ($59/mo) are the only paid tools worth considering.

## Steps that need you, whatever the tooling

- **Creating each new app record in App Store Connect.** Apple's API refuses it ("The resource 'apps' does not allow 'CREATE'"); fastlane `produce` needs your Apple ID and a 2FA code. About 5 minutes per new app. ([details](https://github.com/andrewralon/app-template/issues/2))
- **Privacy labels** for each new app: also Apple ID + 2FA only, no API key route. ([fastlane docs](https://docs.fastlane.tools/uploading-app-privacy-details/))
- **The approval tap.** Keep this on purpose: it's what keeps the account safe.

Everything after the app record exists (builds, metadata, screenshots, submission, updates) runs with an API key, no 2FA.

## On reverse-engineering the paid tools

Don't call Sensor Tower's or AppMagic's private APIs: it breaks their terms, and their value is a model trained on panel data you can't copy anyway. The free rebuild above (charts + rating velocity + reviews) covers most of what an indie needs; our collector already does the rating-velocity part.

## Rules to bake into the build step

- New name, icon and design; never another developer's name or icon (4.1(c), added Nov 2025).
- At least one "meaningfully different" feature, stated in the review notes.
- Each app must do a different job. Several apps from one template that differ only in content count as spam under 4.3(a) ("Don't create multiple Bundle IDs of the same app"). This also applies to the test-prep idea: Part 107 and Exam P may need to be one app with exam packs, the way Pocket Prep groups exams by field.
- No code downloaded or generated at runtime (2.5.2): the reason Apple pulled vibe-coding apps in March 2026.
- Avoid the categories Apple names as saturated: dating, flashlight, sound effects, wallpaper, simple timers, fortune telling.

## Suggested first build

Phase 1 (free, no Apple account needed): add top-charts snapshots and review mining to the collector, and a Claude routine that reads each morning's data and writes a short "candidate of the day" brief: the niche, the leader, its top complaints, and the proposed difference. Phase 2: the shared Expo starter and the build-to-TestFlight step. Phase 3: fastlane submission behind your approval.

## Revenue model (added 2026-10-15)

**Don't train on AppMagic.** Its terms (Sensor Tower's, covering AppMagic) forbid using the service "to build any software, product, or service that is competitive or similar" (3E), making derivative works of its data (3B), and any automated scraping (3M); free access can be revoked at any time. Manual spot checks of a single competitor for your own decisions are fine. ([terms](https://appmagic.rocks/legal/TermsOfService.pdf))

**Rank-only models miss indie apps.** The US top-100 overall grossing chart starts around $230K a day of App Store spend (~$6.8M a month) ([AppTrendKit](https://www.apptrendkit.com/app-store-downloads-by-rank)), so the rank-to-revenue power law (revenue ≈ A × rank^-0.85 to -0.95) only covers big apps, or indie apps high on a category chart. Vendors quote ±2x bands even there ([openaso](https://openaso.ai/reference/revenue-estimates)).

**Verified-revenue directories are out too (corrected 2026-10-15).** TrustMRR's API terms (acceptable use 9.3) forbid workflows that identify successful startups to clone and forbid training or evaluating models on its data; Verified Revenues was returning errors. So there is no free, permitted set of real revenue numbers to train on.

**Model in use (phase 1 trend scout).** A transparent formula instead of a trained model, in `trend.mjs` in the keyword tracker:
- Apps on the overall US grossing chart: daily spend by rank, interpolated from AppTrendKit's published medians (rank 1 about $2.3M a day, 10 about $1.1M, 25 about $510K, 50 about $350K, 100 about $230K).
- All other apps: estimated daily downloads (rating growth × 70) × 30 × the price for paid apps, or × a 12-month revenue per US install (Adapty 2026: Health & Fitness ~$2.40, Utilities ~$2.20; Games $0.50; other genres $1.50, guessed).
- Every estimate carries a low and high value at ÷3 and ×3. Once one of your apps is live, its App Store Connect numbers replace the guessed per-install values.
