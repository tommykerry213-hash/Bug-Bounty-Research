# Bullish - Shared tradingAccountId Research [NA - Educational]

**Target:** simnext.bullish-test.com
**Finding:** Same `tradingAccountId 111490729270459` returned for 2 distinct users via WebSocket `private-data`.

**Steps:**
1. Created user A + user B
2. WebSocket captured: `wss://simnext.bullish-test.com/trading/ws`
3. ZAP Search showed 80 occurrences of same ID
4. Screenshot proof (4 images)

**Result:** Not Applicable - Bugcrowd triage confirmed test environment uses hardcoded demo accounts. Valid lesson on synthetic vs production data.

**Learning:** Always verify same behavior on prod `api.bullish.com` before submitting.

**Status:** Methodology reused for Pinterest hunting.
