---
date: 202408250451
aliases: []
---

# Metadata
Status :: #🌱 #🌼 #🌲 <br>
Note Type :: #📝 #🗺️ <br>
Source URL :: []() <br>
Source Type :: #(想法、書籍、網路文章、影片、課程、Podcast、PDF/電子書、聊天、貼文。)<br>
Author :: #(The Information Author)<br>
Topics :: #(紀錄筆記相關的主題 (MOC)，主題 (MOC) 依據需要會不斷新增。例如時間管理、專案管理、產品管理...等。) <br>
Split :: [[2024-08-24]] <br>

---

# Evergreen Note

Question :: What this note talking about? <br>
-> <br>
Answer :: (My answer) <br>

---

# Ubuntu FAQ
## boot storage is too small
1. You have to divide boot partition first when you install Ubuntu
## Can't boot Ubuntu
 1. Use `boot-repair`
 2. Problem on GRUB
	 1. Reinstall
 3.  You need to install EFI on Fat32 partition
	 1. Don't forget to set `esp` and `boot` flag
## GRUB show command line
1. set root
2. set prefix
3. insmod normal
4. normal
5. start the system
