---
date: 202405021412
aliases: []
---

# Metadata
Status :: #🌱 #🌼 #🌲 <br>
Note Type :: #📝 #🗺️ <br>
Source URL :: []() <br>
Source Type :: #(想法、書籍、網路文章、影片、課程、Podcast、PDF/電子書、聊天、貼文。)<br>
Author :: #(The Information Author)<br>
Topics :: #(紀錄筆記相關的主題 (MOC)，主題 (MOC) 依據需要會不斷新增。例如時間管理、專案管理、產品管理...等。) <br>
Split :: [[2024-05-02]] <br>

---

# Evergreen Note

Question :: What this note talking about? <br>
-> <br>
Answer :: (My answer) <br>

---

# Compress & Extract in Ubunutu
## ZIP
### Multiple file
1. Split
2. Use Default
	1. Compress with password
		1. `zip -e -r {folder name} {output zip}`
	2. Split
		3. `zip -s 20m {target zip} --out {output name}`
	3. Combine
		1. `zip -F {target zip} {output zip}`
	4. Extract
		1. `unzip -P {password} -q {target zip}`
