# Tidy the folder
## ZIP
### Split on Ubuntu
1. `zip -s 20M [sourceFile.zip] --out [split.zip]`
### Concatenate on Ubuntu
1. `zip -s 0 [split.zip] --out [concatenate.zip]`

## Split
### Split on Ubuntu
1. `split -b 20M [sourceFile.zip] [split-part]`
### Unsplit on Ubuntu
1. `cat split-part* > [unsplit.zip]`
2. Extract `[unsplit.zip]`

