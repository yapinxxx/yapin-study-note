---
date: 202509051538
aliases: []
---

# Metadata
Status :: #🌱 #🌼 #🌲 <br>
Note Type :: #📝 #🗺️ <br>
Source URL :: []() <br>
Source Type :: #(想法、書籍、網路文章、影片、課程、Podcast、PDF/電子書、聊天、貼文。)<br>
Author :: #(The Information Author)<br>
Topics :: #(紀錄筆記相關的主題 (MOC)，主題 (MOC) 依據需要會不斷新增。例如時間管理、專案管理、產品管理...等。) <br>
Split :: [[2025-09-05]] <br>

---

# Evergreen Note

Question :: What this note talking about? <br>
-> <br>
Answer :: (My answer) <br>

---

# 我無想欲 hông 消失
# 對零開始，三十工備份社交網路(台文書寫) - Day1

## 介紹

個人使用著的社交軟體有 FB, IG, Thread, Telegram, Line, LinkedIn, Discord, GitHub，Gmail， PTT, Dcard

但是遮的物件基本上攏掌握踮咱時常講著的「科技巨頭」身上，致使咱雖然踮臺灣有充分言論自由，但是踮遮的軟體煞定定需要自我進行言論審查。

所以為著破解這種齷齪的處境，家己決定欲備份遮屬於個人的社交網路，雖然初期應該是閣做袂到自動化 CI/CD 但是希望這三十工會使予代誌有一个頭。


## 結構

1. 核心會依個人的 Blog 為主，因為若是無所在收集社交痕，按呢其實就算講有關聯圖，你嘛會袂記得，發生過啥物代誌，恁是啥物關係，尤其 social media 的小名、相片，時常會變來變去，這對我誠困擾
	1. 所以一開始我會先介紹簡單的 blog 欲按怎建立佮 deploy
		1. 技術採用相對簡單的 Hexo + Github Pages
2. 過來欲挑戰用 Vue + Nuxt + SQLite + Gin + OpenAPI + D3 做一个會使簡單 CRUD 的網路圖
	1. 初期資料應該是依賴人工 maintain
	2. 我本底有計畫 3 个部份 「Relationship」， 「Interested things, hobby」， 「Daily life necessary information, and sold on」，但是「Relationship」的內容會牽涉隱私，所以干焦會 demo 「Interested things, hobby」 的部份，「Daily life necessary information, and sold on」 佮未來 Daily, Realtime 的功能有關，所以暫時先袂實做

## 補充
1. 雖然我是全端工程師，毋過前端實在罔做罔學，所以可能會拄著誠濟困難
	1. 而且根據家己實務經驗，其實設計比實做重要傷濟，所以這系列，比起實做，會閣較濟關心設計
	2. 因為我是將這斗的活動當做專案開發的練習，所以加減會有 workaround 情形產生，所以千萬莫照抄碼文，因為無彼个價值
2. 採用 Agile 開發模式，1～5 sprint, 6、7 專心 Code Review 佮調整設計、目標，因為我是 Extrovert guy, 我是無可能犧牲我的假日踮厝咧！！！
	1. 其實是𬦰山、Party、𨑨迌、Music Festival 、攏規畫好矣
	2. 因為 code review 毋免受地點、設備限制，坐火車、歇睏攏會使做
	3. 𬦰山、聽音樂嘛會使繼續思考專案按怎改進，所以拜六、禮拜實在誠適合做 manager 的工課！
