---
date: 202301301816
aliases: []
---

# Metadata
Status :: #🌱<br>
Note Type :: #📝 #🗺️ <br>
Source URL :: []() <br>
Source Type :: #網路文章<br>
Author :: #(The Information Author)<br>
Topics :: #(紀錄筆記相關的主題 (MOC)，主題 (MOC) 依據需要會不斷新增。例如時間管理、專案管理、產品管理...等。) <br>
Split :: [[2023-01-30]] <br>

---

# Evergreen Note

Question :: What this note talking about? <br>
-> <br>
Answer :: (My answer) <br>

---

# Access Control
## PERM (Policy, Effect, Request, Matchers)

### Syntax for Models
source: [Syntax for Models](https://casbin.org/docs/syntax-for-models)

#### Matchers

`[matchers]` is the definition for policy matchers. The matchers are expressions. It defines how the policy rules are evaluated against the request.

```
[matchers]m = r.sub == p.sub && r.obj == p.obj && r.act == p.act
```

The above matcher is the simplest, it means that the subject, object and action in a request should match the ones in a policy rule.

You can use arithmetic like `+, -, *, /` and logical operators like `&&, ||, !` in matchers.
