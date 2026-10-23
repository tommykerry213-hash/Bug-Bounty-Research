# Tomiwa Omoyungbo | SOC Analyst & AppSec Researcher
Lagos, NG | EMEA Remote | Bugcrowd Hunter

## Methods
I document reproducible methods for Flask API + ReactJS targets.

### 1. IDOR via Shared Account IDs
**Tool:** OWASP ZAP
**Flow:**
1. Create Account A and Account B
2. Proxy both logins via ZAP
3. Search history for `accountId`, `tradingAccountId`, `board_id`, `user_id`
4. In ZAP > Search > `tradingAccountId` -> check if same ID appears for different sessions
5. Reproduce: Use Account B's auth token to request Account A's ID

**Example:** Bullish simnext - `tradingAccountId: 111490729270459` appeared 80 times across 2 accounts (simnext - identified as synthetic test data - Not Applicable - documented as learning).

### 2. WebSocket Private Data Leak
- Connect to `wss://api.[target].com`
- Capture messages containing `tradingAccountId`, `privateData`
- Compare payloads between two users

### 3. ZAP Search Technique
- Sites > History > Search > regex: `(board_id|pin_id|user_id).{10,20}`
- Saves 2 hours vs manual.

## Current Focus
- Target: `api.pinterest.com` (Flask) - Bugcrowd P1 $10k-$25k
- Hunting: Private board IDOR, pin enumeration

## Tools
OWASP ZAP, Burp Suite, Kali Linux

Connect on LinkedIn: Tomiwa Omoyungbo
