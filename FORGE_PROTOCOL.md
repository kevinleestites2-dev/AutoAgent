# The Forge — AutoAgent Prime Manufacturing Protocol

## What This Is
AutoAgent is the manufacturing layer of the Pantheon. Every new Prime
starts here as a natural language description and exits as deployed code.

## The Protocol

### Step 1 — Write the Prime Brief
Describe the Prime in one paragraph. Be specific:
- What data does it consume?
- What does it do with that data?
- Where does it send output?
- What triggers it?

### Step 2 — Feed to AutoAgent Agent Editor
```bash
auto main
# Choose: agent editor
# Paste the Prime Brief
# AutoAgent profiles, builds tools, generates code
```

### Step 3 — Review Generated Agent
AutoAgent outputs:
- Agent profile (role, personality, constraints)
- Tool list (auto-generated Python functions)
- Workflow DAG (execution order)

### Step 4 — Wire to Pantheon
- Add Telegram reporting token (TOOLS.md)
- Connect to existing data sources (LEEPA, Polymarket, etc.)
- Deploy as GitHub Actions workflow or Termux background process

### Step 5 — SAFLA Loop
Feed agent performance back through SAFLA v2 for continuous improvement.

---

## Prime Briefs — Ready to Build

### ScoutPrime v5
"Build a real estate scout agent for Lee County, Florida. It should
scrape PropertyOnion.com for upcoming auction listings, look up each
property on LEEPA (leepa.org) to get square footage, bedrooms, year
built, and current owner. Then pull the Zillow estimate for each address.
Calculate the spread between auction starting bid and Zillow value.
Filter for spreads above $50,000. Send a formatted Telegram message with
the top 5 opportunities every morning at 7am."

### ArbitrageScout
"Build a prediction market arbitrage agent. Monitor Polymarket and Kalshi
for the same event with different odds. When the implied probability
differs by more than 3%, calculate the hedge position sizes for guaranteed
profit. Send a Telegram alert with the trade sizes and expected profit.
Use the existing Polymarket API credentials."

### SentinelPrime
"Build a system health monitor for the Pantheon. Every 30 minutes, check:
GitHub Actions workflow status for CloakPrime (GhostPrime), ContentPrime,
and ScoutPrime repos. Check the Adsterra dashboard for impression count.
Check OpenAgora war chest balance. If anything is down or below threshold,
send a Telegram alert immediately."
