
## Find and remove duplicates
[https://stackoverflow.com/questions/37992493/how-can-i-remove-duplicate-lines-in-visual-studio-code](https://stackoverflow.com/questions/37992493/how-can-i-remove-duplicate-lines-in-visual-studio-code)

Sort lines alphabetically, if they aren't already, and perform these steps:
(based on this related question: How do I find and remove duplicate lines from a file using Regular Expressions?)

 - Control+F
 - Toggle "Replace mode"
 - Toggle "Use Regular Expression" (the icon with the `.*` symbol) *next to the search field*
 - In the search field, type `^(.*)(\n\1)+$`
 - In the "replace with" field, type `$1`
 - Click the Replace All button ("Replace All").

**If the order of lines is important so you can't sort**
In this case, either resort to a solution outside VS Code, or - if your document is not very large and you don't mind spamming the Replace All button - follow the previous steps, but in steps 4 and 5, enter these:
(based on Remove specific duplicate lines without sorting)

Caution: Blocks for files with too many lines (1000+); may cause VS Code to crash; may introduce blank lines in some cases.

search: `((^[^\S$]*?(?=\S)(?:.*)+$)[\S\s]*?)^\2$(?:\n)?`

replace with: `$1`

**Warning, the latter step may crash VS Code**


## View Diff of different files
You can diff any two files by first right clicking on a file in the EXPLORER or OPEN EDITORS list and selecting Select for Compare and then right-click on the second file to compare with and select Compare with <file_name_you_chose>.

Alternatively from the keyboard hit `Ctrl (cmd) + Shift + P` and select `menu File → Compare Active File With...` and you will be presented with a list of recent files. 
See also - https://stackoverflow.com/a/51317507/3795116
