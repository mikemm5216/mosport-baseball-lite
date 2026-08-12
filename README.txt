MOSPORT Baseball Life — Offseason Market / Contract / Trade hotfix v2

Target repo: mikemm5216/mosport-baseball-lite
Target production: https://mosport-baseball-lite.vercel.app/

ADD THESE TWO FILES TO THE REPOSITORY ROOT:
1. patched.html
2. vercel.json

Keep the current index.html unchanged.
Commit and push main. If this Vercel project is connected to the repo, the push should trigger a new deployment.

WHAT THIS FIXES
- Replying to a recruiting/market contact no longer only increases a percentage and then skips to the next year.
- "Confirm replies" starts actual follow-up event cards, one contact at a time.
- Pro offseason can resolve:
  * original-team renewal and negotiation
  * CPBL trade while under contract
  * CPBL free-agent signing after contract expiry
  * NPB / KBO / MLB overseas development or contract route
  * national-team call-up decision
- Accepted transactions update team, contract, role, membership history, career log, and market history.
- Professional contract years tick down after a completed season.
- An expired contract can no longer silently advance into another season; a final contract-choice event is required.
- Current contract appears in the sidebar.
- MARKET is preserved when reloading a save instead of being incorrectly converted to FLOW_RESUME.
- After an overseas signing, regular-season competition/opponents and postseason names switch to NPB/KBO/MLB rather than continuing to display CPBL.
- Pre-pro replies also generate formal follow-up interview/test/recruitment events.

IMPLEMENTATION NOTE
This is a production hotfix loader pinned to the current index.html structure. It fetches the existing /index.html, patches the affected functions before that page executes, and then renders the patched game. This avoids replacing the entire current 160KB+ index.html while GitHub write access is unavailable through the connected integration.

LONG-TERM
Once repository write access is available, merge the same logic directly into index.html and remove patched.html + the root rewrite.
