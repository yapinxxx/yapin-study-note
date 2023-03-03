---
date: 202301171432
aliases: []
---

# Metadata
Status :: #🌱  <br>
Note Type :: #📝  <br>
Source URL :: []() <br>
Source Type :: #myself  <br>
Author :: #IBG <br>
Topics :: #obsidian <br>
Split :: [[2023-01-16]]

---
# Obsidian Plugins Note
## Plugins 
Obsidian Plugins was composed by ==manifest.json==, ==main.js==, ==style.css== *(Can use CSS to control the plugin style)*

### Calendar
Record the daily note

### Dataview
A convenience tool about search the note

### Note-Refactor
Very helpful to refactor the note
1. Split the note by heading format (Refactor the reading note)
	1. Turn on ==Exclude First Line== so that the auto split can work as expected
	2. Turn off the ==Include Heading== and use the template to control the content of the new note.
2. Extract the content from the note

### LanguageTool
1. Spell check tool
2. Store the personal word in `Your-Vault/.obsidian/app.json`
	1. Example:  
		```json
		{
			"spellcheckDictionary": [
				"json"
			],
		}
		```
	2. Obsidian have the official spell check under Setting > Editor > Spellcheck
		1. The official ==Spellcheck dictionary== is located on `.config/obsidian/Custom Dictionary.txt` *(on Ubuntu)*
