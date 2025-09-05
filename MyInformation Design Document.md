---
date: 202508211318
aliases: []
---

# Metadata
Status :: #🌱 #🌼 #🌲 <br>
Note Type :: #📝 #🗺️ <br>
Source URL :: []() <br>
Source Type :: #(想法、書籍、網路文章、影片、課程、Podcast、PDF/電子書、聊天、貼文。)<br>
Author :: #(The Information Author)<br>
Topics :: #(紀錄筆記相關的主題 (MOC)，主題 (MOC) 依據需要會不斷新增。例如時間管理、專案管理、產品管理...等。) <br>
Split :: [[2025-08-21]] <br>

---

# Evergreen Note

Question :: What this note talking about? <br>
-> <br>
Answer :: (My answer) <br>

---

# MyInformation Design Document
OK, I will separate this project in multiple parts, you should help me to confirm whether logic or design have error

Summary
1. This project main target is control the personal information, and get back the time belong to ourselves
2. So our information will have multiple aspects
    1. Relationship
	    1. about our friends, family, co-worker, community, online friend, probability friend, dislike people, and sold on.
    2. Interested things, hobby
	    1. Like skills, acknowledge, idol, courses, animal, store, books, race, music, movie, probability interesting things
	3. Daily life necessary information, and sold on.
		1. Discount, News, government information, company message, stock, new law, society issues, politics, tax, accounting, credit card message, activity notification, pet information, and sold on.
3. We need a tool to make it more visualization, and make it help us follow, track and control our life.

Ability
1. Now we could know some important things
	1. Visualization
	2. Customize Database
	3. Tidy information
		1. Automation to notify us the information
		2. Summary the daily life information by A.I.
		3. Decrease our routine and spend our more spirit to care about what we really interested

Technology
1. Frontend
	1. Platform
		1. Mobile Phone
		2. Computer
		3. E-Ink Reader
	2. Features
		1. Visualization
		2. Friendly control
			1. Easy load information
			2. Auto store the information
		3. Easy backup
		4. Security
			1. Self-Host
			2. Cloud
				1. Business Model
					1. Use hash to connect different people
					2. Target for organization, company, foundation
					3. Convenience tools for personal user
					4. Be a security and 
2. Backend
	1. Use color label to distinguish the custom visit heat
	2. Use SQL database first
	3. These data are very valuable, so the security is very important
		1. Only user could get the data
		2. But I'm not sure if I create PWA application, could I access the data from the mobile phone? I think is not, because PWA still a client-server application, the server is host remote.
3. Use OpenAPI to generate the struct for frontend and backend
