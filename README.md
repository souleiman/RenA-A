Requirements
------------
* Java 8 (Lambda support)
* Dependencies can be found in lib/dependencies.txt

Usage
-----
	java -jar bin/RenA.jar entities [ngram] [name_ent_bool] [org_ent_bool] [loc_ent_bool] [FileOrFolder] [classifier] [stopwords]
	java -jar bin/RenA.jar attributes [FileOrFolder] [classifier] [stopwords]

Example
--------
    #For named entity extraction for a single file,
    java -jar bin/RenA.jar entities 2 true true true filename.txt commons/classifier/rena.cls commons/stopwords/ > output.txt

    #For directory,
    java -jar bin/RenA.jar entities 2 true true true path_to_directory/ commons/classifier/rena.cls commons/stopwords/ > output.txt

    #For Attribute extraction,
    java -jar bin/RenA.jar attributes filename.txt commons/classifier/rena.cls commons/stopwords/ > output.txt
    
    #For Multiple File Attribute extraction,
    java -jar bin/RenA.jar attributes path_to_directory/ commons/classifier/rena.cls commons/stopwords/ > output.txt   
    
Output
------
Results will be displayed in JSON, consisting of:

    filename    - name of the file analyzed
    PERS        - Names extracted from entities
    ORG         - Organizations extracted from entities
    LOC         - Locations extracted from entities
    date        - Date extracted from attributes if any
    author      - Author of the article from attribute if any
    title       - Title of the article extracted from attribute