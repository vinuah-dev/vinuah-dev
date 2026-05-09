# .github/workflows/snake.yml
# This workflow generates the animated snake contribution graph
# Place this file at: .github/workflows/snake.yml in your vinuah-dev/vinuah-dev repository

name: Generate Snake Animation

on:
  schedule:
    - cron: "0 */12 * * *" # Runs every 12 hours
  workflow_dispatch: # Allows manual trigger

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Generate Snake Game
        uses: Platane/snk@v3
        with:
          github_user_name: vinuah-dev
          outputs: |
            dist/github-snake.svg
            dist/github-snake-dark.svg?palette=github-dark

      - name: Push to output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
