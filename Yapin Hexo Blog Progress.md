---
date: 202404200037
aliases: []
---

# Metadata
Status :: #🌱 #🌼 #🌲 <br>
Note Type :: #📝 #🗺️ <br>
Source URL :: []() <br>
Source Type :: #(想法、書籍、網路文章、影片、課程、Podcast、PDF/電子書、聊天、貼文。)<br>
Author :: #(The Information Author)<br>
Topics :: #(紀錄筆記相關的主題 (MOC)，主題 (MOC) 依據需要會不斷新增。例如時間管理、專案管理、產品管理...等。) <br>
Split :: [[2024-04-19]] <br>

---

# Evergreen Note

Question :: What this note talking about? <br>
-> <br>
Answer :: (My answer) <br>

---

# Yapin Hexo Blog Progress
## Prepare Tools
### Git
#### Ubuntu
1. Use `sudo apt install git`
	1. apt is good to control
### Node.js
#### Ubuntu
1. Use NVM to install node
	1. Because node have many version and in business you usually have to switch many different version to solve development environment problem
	2. NVM is an opensource (based on bash script)
	3. [NVM GitHub Repository](https://github.com/nvm-sh/nvm)
2. Check NPM Gloabl Install Location
	1. `npm root -g`
	2. NPM is a big problem to do project manager
		1. NVM can help control this problem 
## Set up Hexo
1. `npm install -g hexo-cli`
2. `npm install hexo`
	1. Once installed, you can run Hexo in two ways:
		1. `npx hexo <command>`
		2. Linux users can set relative path of `node_modules/` folder:
			`echo 'PATH="$PATH:./node_modules/.bin"' >> ~/.profile`
			then run Hexo using `hexo <command>`
