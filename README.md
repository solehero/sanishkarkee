<div align="center">
  <table>
    <tr>
      <td width="20%">
        <img src="https://i.giphy.com/3NjABnBOieYQE4BpkP.webp" width="100%" style="border: none;" />
      </td>
      <td width="80%" style="border: none;">
<div>

[![GitHub WidgetBox](https://github-widgetbox.vercel.app/api/profile?username=sanishkarkee&data=followers,repositories,stars,commits&theme=metropolis)](https://github.com/sanishkarkee)
</div>
      </td>
    </tr>
  </table>
</div>
<br>
<img src="https://i.imgur.com/dBaSKWF.gif" height="20" width="100%">

# 💫 About Me:
Currently mastering the art of staring at the screen until inspiration hits. 
<br><br>

# 💬 Hey lets get connected
[![Instagram](https://img.shields.io/badge/Instagram-%23E4405F.svg?logo=Instagram&logoColor=white)](https://instagram.com/sanishkarki007) [![LinkedIn](https://img.shields.io/badge/LinkedIn-%230077B5.svg?logo=linkedin&logoColor=white)](https://linkedin.com/in/sanish-karki-680249148) [![Reddit](https://img.shields.io/badge/Reddit-%23FF4500.svg?logo=Reddit&logoColor=white)](https://reddit.com/user/Ambitious_Occasion_9) [![YouTube](https://img.shields.io/badge/YouTube-%23FF0000.svg?logo=YouTube&logoColor=white)](https://youtube.com/@@simplifiedfactzz) [![email](https://img.shields.io/badge/Email-D14836?logo=gmail&logoColor=white)](mailto:s.karki1994@gmail.com) 
<br><br>
# 🚀 Some Tools I Have Used and Learned
<p align="left">
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/html5/html5-plain-wordmark.svg" alt="html5" width="45" height="45" />&nbsp;&nbsp;&nbsp;&nbsp;    
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/css3/css3-plain-wordmark.svg" alt="css3" width="45" height="45"/>&nbsp;&nbsp;&nbsp;&nbsp; 
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/sass/sass-original.svg" alt="SCSS" width="45" height="45"/>&nbsp;&nbsp;&nbsp;&nbsp;  
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/javascript/javascript-plain.svg" alt="javascript" width="45" height="45"/>&nbsp;&nbsp;&nbsp;&nbsp;  
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/react/react-original.svg"  alt="React" width="45" height="45"/>&nbsp;&nbsp;&nbsp;&nbsp; 
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/redux/redux-original.svg" alt="reduxToolkit" width="45" height="45"/>&nbsp;&nbsp;&nbsp;&nbsp;  
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/tailwindcss/tailwindcss-original.svg" alt="Tailwind" width="45" height="45"/>&nbsp;&nbsp;&nbsp;&nbsp;
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/figma/figma-original.svg" alt="figma" width="45" height="45"/>&nbsp;&nbsp;&nbsp;&nbsp; 
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/docker/docker-original.svg" alt="Docker" width="45" height="45"/>&nbsp;&nbsp;&nbsp;&nbsp;
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/github/github-original-wordmark.svg" alt="=Github" width="45" height="45"/>&nbsp;&nbsp;&nbsp;&nbsp;  
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/trello/trello-plain-wordmark.svg" alt="Trello" width="45" height="45"/>&nbsp;&nbsp;&nbsp;&nbsp; 
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/jira/jira-original-wordmark.svg" alt="Jira" width="45" height="45"/>&nbsp;&nbsp;&nbsp;&nbsp;     
</p>
<br><br>
<h2> 📈 My Github History!</h2>
<p align="left">
<div style="display: flex; justify-content: flex-start; align-items: center; ">
  <img src="https://github-readme-stats.vercel.app/api?username=sanishkarkee&show_icons=true&theme=tokyonight" height="200"/>
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=sanishkarkee&theme=tokyonight"  height="200"/>
</div>
<p/>
<br><br>

name: generate animation

on:
  # run automatically every 24 hours
  schedule:
    - cron: "0 */24 * * *" 
  
  # allows to manually run the job at any time
  workflow_dispatch:
  
  # run on every push on the master branch
  push:
    branches:
    - master
    
  

jobs:
  generate:
    permissions: 
      contents: write
    runs-on: ubuntu-latest
    timeout-minutes: 5
    
    steps:
      # generates a snake game from a github user (<github_user_name>) contributions graph, output a svg animation at <svg_out_path>
      - name: generate github-contribution-grid-snake.svg
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark
          
          
      # push the content of <build_dir> to a branch
      # the content will be available at https://raw.githubusercontent.com/<github_user>/<repository>/<target_branch>/<file> , or as github page
      - name: push github-contribution-grid-snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}






















