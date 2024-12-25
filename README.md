# BTC Lottery

A GitHub Action that performs a lottery draw using Bitcoin's latest block hash as a random seed.

## How It Works

1. **Random Seed Generation**
   - Fetches the latest Bitcoin block hash from blockchain.info
   - Uses the last 8 characters of the hash as a random seed
   - Ensures transparency and verifiability of the lottery process

2. **Lottery Process**
   - Uses Python's `random.sample()` with the BTC-based seed
   - Draws unique numbers from the defined pool
   - Results are saved in both JSON and Markdown formats

3. **Schedule**
   - Runs daily at 09:00 UTC (as set)
   - Can also be triggered manually via workflow_dispatch

## Configuration

You can customize the lottery by modifying the environment variables in the workflow file:
```yaml
env:
POOL_SIZE: 15 # Total number of tickets (1 to POOL_SIZE)
WINNER_COUNT: 2 # Number of winners to draw
```

To modify these values:
1. Edit `.github/workflows/btc-lottery.yml`
2. Update `POOL_SIZE` and `WINNER_COUNT` as needed
3. Commit and push your changes

## Results

After each run, you can find:
- Detailed results in the Actions tab
- Two artifacts are generated:
  - `lottery-results.json`: Raw JSON data
  - `lottery-summary.md`: Formatted markdown summary

Example result format:

### 🎲 Lottery Results (2024-04-17)
Block Information

Block Hash: 000000000000000000016b3...

Random Seed: 123456789

### Lottery Results
Pool Size: 15

Number of Winners: 2

🎉 Winning Numbers: 7, 13


## Manual Trigger

To run the lottery manually:
1. Go to the "Actions" tab
2. Select "BTC Lottery"
3. Click "Run workflow"
4. Click "Run workflow" in the popup



