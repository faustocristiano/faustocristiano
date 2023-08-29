name: Update Commit Summary

on:
  push:
    branches:
      - main # Ou a branch que você deseja monitorar

jobs:
  update_summary:
    runs-on: ubuntu-latest
    steps:
      - name: Check Out Repository
        uses: actions/checkout@v2

      - name: Update Commit Summary
        run: |
          # Coloque aqui o script ou comando que gera o resumo dos commits
          # Você pode usar ferramentas como git log para coletar informações dos commits

      - name: Commit and Push Changes
        run: |
          git config --local user.email "your-email@example.com"
          git config --local user.name "Your Name"
          git add commit_summary.md
          git commit -m "Update commit summary"
          git push
