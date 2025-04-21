---
Title: Publishing Notes
Status: 
marker: 
tags: 
Date: 2024.08.17
Time: 17:58
---
# Publishing Notes
This note covers a description of the steps I take to try to publish my obsidian notes in the best way possible.
These can be followed to recreate one yourself.

# Private and Public
Firstly the private files need not to be published to github will be set on a git ignore file so that they are not pushed. This saves my headache of worrying if my private notes will be published or not.
This is my current push gitignore file.
```gitignore
#* = ignoring everything

*

#Except these files since these are not ignore files

!attachments/

!Btech Third Semester/

!Publish verification folder/

!templates/

!Programming/

#always ignore

private/

.obsidian/

Main Note/
```

- `#` Means comments
- `*` Means everything in the directory
- `!` Prefixed to a directory implies that directory shall NOT BE IGNORED.
- simply stating directories in this file like private/ will ignore it.
for more refer [[gitignore]]

# Hosting



# References


###### Information
- date: 2024.08.17
- time: 17: