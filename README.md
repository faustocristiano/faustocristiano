name: Update GitHub Stats

on:
  push:
    branches:
      - main

jobs:
  update_stats:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Repository
        uses: actions/checkout@v2

      - name: Update Stats
        run: |
          echo "Total Commits: $(git rev-list --count HEAD)" > stats.md

      - name: Commit and Push Changes
        run: |
          git config --local user.email "your-email@example.com"
          git config --local user.name "Your Name"
          git add stats.md
          git commit -m "Update stats"
          git push
