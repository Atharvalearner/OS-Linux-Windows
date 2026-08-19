***# sed Command:*** 

* an acronym for stream editor. 
* It is used for editing a file without using an editor. 
* The SED command performs a variety of operations on files, such as searching, finding and replacing, inserting and deleting. However, substitution or find and replace are the most commonly used features of SED.



Syntax: sed options file 



Example: Execution over Shell Interpreter/Editor

> echo "Hi Gourav" | sed 's/Hi/Hello/' 		.. “s” command in sed replaces the string Hi with “Hello”. 





***# awk Command:*** 

* generally used to manipulate data and generate reports. 
* There is no need to compile it and users are allowed to have access to a variable, string functions, numeric functions, and logical operations.



Syntax: awk options File Name 



Example: Execution over Shell Interpreter/Editor 

> awk ‘{print $2}’ script10 			.. Print only 2nd Column content

