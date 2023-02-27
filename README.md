<!--
**mwormley008/mwormley008** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->

[![GitHub Streak](https://streak-stats.demolab.com/?user=mwormley008)](https://git.io/streak-stats)

![Codewars](https://github.r2v.ch/codewars?user=mworm&stroke=yellow)

![Leetcode Stats](https://leetcard.jacoblin.cool/mworm)

<a href="https://data.typeracer.com/pit/profile?user=mwormley&ref=badge" target="_top"><img src="https://data.typeracer.com/misc/badge?user=mwormley" border="0" alt="TypeRacer.com scorecard for user mwormley"/></a>

[monkeytype.badge]: https://img.shields.io/endpoint?style=flat&url=https%3A%2F%2Fmonkeytype-badge-vhd5lan7mmhz.runkit.sh
[![monkeytype.badge]](https://monkeytype.com/)
# .github/workflow/monkeytype.yaml
name: Monkeytype Readme

on:
  # Runs if triggered manually through github action console
  workflow_dispatch:
  schedule:
    # Runs at 00:00 each sunday
    - cron: '0 0 * * 0'

jobs:
  update-readme:
    name: Update README
    runs-on: ubuntu-latest
    # it shouldn't take longer than a few minutes
    # but leave a timeout here in case request hangs
    timeout-minutes: 10
    steps:
      - uses: vnphanquang/monkeytype-readme@main
        with:
          # required:
          monkeytype_api_key: ${{ secrets.MONKEYTYPE_API_KEY }}
          mode: 'time'
          mode2: '30'
          # not required with default:
          style: 'flat' # option from shields.io
          logoVariant: 'one'
          label: 'monkeytype'
  # outputs badge_url should you need to use that in later steps
