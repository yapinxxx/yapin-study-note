---
date: 202310021027
aliases: []
---

# Metadata
Status :: [[🌱]] [[🌼]] [[🌲]] <br>
Note Type :: [[📝]] [[🗺️]] <br>
Source URL :: []() <br>
Source Type :: #(想法、書籍、網路文章、影片、課程、Podcast、PDF/電子書、聊天、貼文。)<br>
Author :: #(The Information Author)<br>
Topics :: #(紀錄筆記相關的主題 (MOC)，主題 (MOC) 依據需要會不斷新增。例如時間管理、專案管理、產品管理...等。) <br>
Split :: [[2023-09-28]] <br>

---

# Evergreen Note

Question :: What this note talking about? <br>
-> <br>
Answer :: (My answer) <br>

---

# Angular Primer
# Angular Environment
1. Install `nvm` script to control `nodejs version` 
2. Choose `v18` version about nodejs
	1. `nvm use (which version do you want)`
3. Use `npm` to install Angular CLI
	1. `npm install -g @angular/cli`
		1. Don't worry about the environment, `nvm` will auto install packages in `./nvm` directory.
		2. You can use `npm -g list` to check your environment


# Angular Project Note
1. Create new Angular project 
	1. `ng new (your project name)`
2. Import necessary module in `app.module.ts`
	1. This depends on which component the developer is using.
	2. Sometimes, you need to use `ng add`, `npm i`, or `yarn add`.
3. Control the `style.scss` to modify the UI
4. Create Angular components
	1. `ng generate component (your component name)`

# Deploy NPM module
1. Sign up NPM website
2. Publish the module
	1. need create `package.json` file
		1. Creator could use `npm init`, `npm install` to help create `package.json`
	2. Login NPM
		1. `npm login`
	3. Deploy Custom Package
		1. Under the folder which have `package.json` and use `npm publish` to deploy
		2. If people can't publish, maybe not yet setting 2FA 