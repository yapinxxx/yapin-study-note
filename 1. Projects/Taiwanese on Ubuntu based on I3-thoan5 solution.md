---
date: 202410312258
aliases: []
---

# Metadata
Status :: #🌱 #🌼 #🌲 <br>
Note Type :: #📝 #🗺️ <br>
Source URL :: []() <br>
Source Type :: #(想法、書籍、網路文章、影片、課程、Podcast、PDF/電子書、聊天、貼文。)<br>
Author :: #(The Information Author)<br>
Topics :: #(紀錄筆記相關的主題 (MOC)，主題 (MOC) 依據需要會不斷新增。例如時間管理、專案管理、產品管理...等。) <br>
Split :: [[2024-10-31]] <br>

---

# Evergreen Note

Question :: What this note talking about? <br>
-> <br>
Answer :: (My answer) <br>

---

# Taiwanese on Ubuntu based on I3-thoan5 solution
There has been some progress in migrating i3-thoan5 from fcitx to fcitx5. After working through the RIME tutorial, I found that i3-thoan has nearly resolved all spelling issues, so the main remaining task is to upgrade the frontend framework.

I’d also like to make it compatible with other operating systems, like Windows and macOS, which will require refactoring i3-thoan5 and creating an adapter module to align it with the RIME project.

Here are my main tasks:

1. My priority is to type Taibun on Ubuntu as soon as possible, so upgrading from fcitx to fcitx5 is the first task.
2. Based on the commit history, I need to integrate two repositories: `fcitx5-Rime` and i3-thoan5’s `librime`.
3. Refactor `librime` to ensure compatibility with RIME.

---

Although this mostly seems like an integration issue, tracing through the code has been exhausting for me. QQ
