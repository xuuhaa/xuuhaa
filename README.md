![Anurag's GitHub stats](https://github-readme-stats.vercel.app/api?username=xuuhaa&show_icons=true&theme=dark)


#Github Action for generating a contribution graph with a snake eating your contributions.

name: Generate Snake

on:
  schedule:
    - cron: "0 0 * * *"
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout
        uses: actions/checkout@v2.3.4
      
      - name: Generate Snake
        uses: Platane/snk@master
        id: snake-gif
        with:
          github_user_name: ${{ github.repository_owner }}
          gif_out_path: ./assets/github-contribution-grid-snake.gif
          svg_out_path: ./assets/github-contribution-grid-snake.svg

      - name: Push to GitHub
        uses: EndBug/add-and-commit@v7.2.1
        with:
          branch: main
          message: 'Generate Contribution Snake'


<!--
**xuuhaa/xuuhaa** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

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
