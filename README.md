<p align="right"> <img src="https://komarev.com/ghpvc/?username=Junsious&label=Profile%20views&color=9d7cd8&size=18&style=for-the-badge" alt="Junsious" /> </p> 


<h3 align="center">
  <img src="https://readme-typing-svg.herokuapp.com/?font=Righteous&size=45&center=true&vCenter=true&width=1600&height=80&duration=5000&color=9d7cd8&lines=Hello!+I'm+Junsious+" />
</h3>

---

-  💾 I'm a Programmer Enthusiast who likes make PC utilities
-  📗 I’m currently learning how to code properly
  
---

### 📶 My Stats : 

![GitHub Summary](http://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=Junsious&theme=tokyonight) 

[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=junsious&layout=compact&hide_border=true&theme=tokyonight)](https://github.com/anuraghazra/github-readme-stats)

[![GitHub Streak](https://github-readme-streak-stats.herokuapp.com?user=Junsious&theme=tokyonight&hide_border=true&date_format=j%20M%5B%20Y%5D&card_width=480)](https://git.io/streak-stats)

---

### 𝚈𝚘𝚞 𝚌𝚊𝚗 𝚊𝚕𝚜𝚘 𝚜𝚞𝚙𝚙𝚘𝚝 𝚖𝚎 :3  

[![donate](https://github.com/user-attachments/assets/95b28df1-cfbb-4b09-ac09-ce5e5ab3c3e3)
](https://www.donationalerts.com/r/junsious)

---

<h3 align="center">
  <img src="https://readme-typing-svg.herokuapp.com/?font=Righteous&size=45&center=true&vCenter=true&width=1600&height=80&duration=5000&color=9d7cd8&lines=Have+a+nice+day!+" />
</h3>

name: generate animation

on:
  # run automatically every 12 hours
  schedule:
    - cron: "0 */12 * * *" 
  
  # allows to manually run the job at any time
  workflow_dispatch:
  
  # run on every push on the master branch
  push:
    branches:
    - main
    
  

jobs:
  generate:
    runs-on: ubuntu-latest
    timeout-minutes: 10    
    steps:
      # generates a snake game from a github user (<github_user_name>) contributions graph, output a svg animation at <svg_out_path>
      - name: Generate github-contribution-grid-snake.svg
        uses: Platane/snk/svg-only@v2
        with:
          github_user_name: Junsious
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark
      # push the content of <build_dir> to a branch
      # the content will be available at https://raw.githubusercontent.com/<github_user>/<repository>/<target_branch>/<file> , or as github page
      - name: Push github-contribution-grid-snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v2.6.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
