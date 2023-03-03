---
date: 202302161001
aliases: []
---

# Metadata
Status :: #🌱 #🌼 #🌲 <br>
Note Type :: #📝 #🗺️ <br>
Source URL :: []() <br>
Source Type :: #(想法、書籍、網路文章、影片、課程、Podcast、PDF/電子書、聊天、貼文。)<br>
Author :: #(The Information Author)<br>
Topics :: #(紀錄筆記相關的主題 (MOC)，主題 (MOC) 依據需要會不斷新增。例如時間管理、專案管理、產品管理...等。) <br>
Split :: [[2023-02-15]] <br>

---

# Evergreen Note

Question :: What this note talking about? <br>
-> <br>
Answer :: (My answer) <br>

---

# Casbin  Note
# Casbin Access Control Model Design (Authorization)

1. 使用 Casbin online editor 測試語法
2. 目前語法不熟悉的地方有幾個
	1. role_definition
		1. 這個與 RBAC 的延伸行設計有關
		2. 目前採用最基本的設計
			1. 一個 group
			2. 一個 group 只含有兩個 role
	2. policy_effect
		1. 需要釐清三個參數 some, where, `eft` 
			1. `eft` default value is `allow`
			2. where ➡ 挑選符合判斷式 (policy) 的描述
			3. some ➡ 邏輯上 (exist)
		2. 這部份先以符合預期設計為主，遇到不符合情形的條件再微調
	3. matchers
		1. 定義何種 request 屬於 true
		2. `g(r.sub, p.sub)` 此條件目前還無法理解
		3. 這個屬性非常特別，判斷式的先後順序會影響處理時間，必須留意
			1. Casbin 官方文件有提到要注意，但沒說清楚為何會發生
			2. 目前看來是 `g(r.sub, p.sub)` 這部份所造成的影響

## Example
1. conf file
	```
	[request_definition]
	r = sub, obj, act
	
	[policy_definition]
	p = sub, obj, act
	
	[role_definition]
	g = _, _
	
	[policy_effect]
	e = some(where (p.eft == allow))
	
	[matchers]
	m = r.obj == p.obj && r.act == p.act && g(r.sub, p.sub)
	```

2. csv file
	```
	p, Administrator, privateData, write
	
	
	p, Operator, privateData, read
	p, Operator, privateData, execution
	p, Operator, normalData, write
	
	
	p, Monitor, normalData, execution
	
	p, Viewer, normalData, read
	
	g, Monitor, Viewer
	g, Operator, Monitor
	g, Administrator,Operator
	```
