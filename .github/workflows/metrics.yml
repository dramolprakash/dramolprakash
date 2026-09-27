name: Metrics
on:
  schedule:
    - cron: "0 6 * * *"   # runs once a day
  workflow_dispatch:       # lets you run it manually from the Actions tab
  push:
    branches: ["main"]

jobs:
  github-metrics:
    runs-on: ubuntu-latest
    permissions:
      contents: write
    steps:
      - uses: lowlighter/metrics@latest
        with:
          token: ${{ secrets.METRICS_TOKEN }}
          user: dramolprakash
          filename: github-metrics.svg
          template: classic
          config_timezone: America/Chicago

          # Core sections
          base: header, activity, community, repositories, metadata

          # "About me" box, filled from your GitHub profile bio
          plugin_introduction: yes

          # Contribution calendar (the 3D green bars)
          plugin_isocalendar: yes
          plugin_isocalendar_duration: half-year

          # Most-used languages across your repos
          plugin_languages: yes
          plugin_languages_limit: 6

          # Achievements plugin left off (it errored on the original card).
          # Followers plugin left off (embedded avatars made the file huge).
