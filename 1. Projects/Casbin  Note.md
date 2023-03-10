---
date: 202302161001
aliases: []
---

# Metadata
Status :: #ð± #ð¼ #ð² <br>
Note Type :: #ð #ðºï¸ <br>
Source URL :: []() <br>
Source Type :: #(æ³æ³ãæ¸ç±ãç¶²è·¯æç« ãå½±çãèª²ç¨ãPodcastãPDF/é»å­æ¸ãèå¤©ãè²¼æã)<br>
Author :: #(The Information Author)<br>
Topics :: #(ç´éç­è¨ç¸éçä¸»é¡ (MOC)ï¼ä¸»é¡ (MOC) ä¾æéè¦æä¸æ·æ°å¢ãä¾å¦æéç®¡çãå°æ¡ç®¡çãç¢åç®¡ç...ç­ã) <br>
Split :: [[2023-02-15]] <br>

---

# Evergreen Note

Question :: What this note talking about? <br>
-> <br>
Answer :: (My answer) <br>

---

# Casbin  Note
# Casbin Access Control Model Design (Authorization)

1. ä½¿ç¨ Casbin online editor æ¸¬è©¦èªæ³
2. ç®åèªæ³ä¸çæçå°æ¹æå¹¾å
	1. role_definition
		1. éåè RBAC çå»¶ä¼¸è¡è¨­è¨æé
		2. ç®åæ¡ç¨æåºæ¬çè¨­è¨
			1. ä¸å group
			2. ä¸å group åªå«æå©å role
	2. policy_effect
		1. éè¦éæ¸ä¸ååæ¸ some, where, `eft` 
			1. `eft` default value is `allow`
			2. where â¡ æé¸ç¬¦åå¤æ·å¼ (policy) çæè¿°
			3. some â¡ éè¼¯ä¸ (exist)
		2. éé¨ä»½åä»¥ç¬¦åé æè¨­è¨çºä¸»ï¼éå°ä¸ç¬¦åæå½¢çæ¢ä»¶åå¾®èª¿
	3. matchers
		1. å®ç¾©ä½ç¨® request å±¬æ¼ true
		2. `g(r.sub, p.sub)` æ­¤æ¢ä»¶ç®åéç¡æ³çè§£
		3. éåå±¬æ§éå¸¸ç¹å¥ï¼å¤æ·å¼çåå¾é åºæå½±é¿èçæéï¼å¿é çæ
			1. Casbin å®æ¹æä»¶ææå°è¦æ³¨æï¼ä½æ²èªªæ¸æ¥çºä½æç¼ç
			2. ç®åçä¾æ¯ `g(r.sub, p.sub)` éé¨ä»½æé æçå½±é¿

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
