***
# Reverse Engineering w/Ghidra
## Pluralsight Course
***
## Module 3
* tools are plugins & their configs (you interact w/these through the tool chest)
* plugins are what make up Ghidra
* the server component lets you collab on a shared project
* when performing auto-analysis, the *analysis options* screen presents you w/diff plugins to use
* Recall, 3 pushes and a call to a function can indicate a call to **main** and the 3 pushes being the 3 args (argc, argv, & envp)
* cross references (XREFs) are every place where a call to that particular function is made

## Main User Interface:

* *Program tree* - provides a high level view of the file format
* *Symbol tree* - provides overview of all program symbols (EX: imports) 
* *Data type manager*- structures & other data types identified
* *Listing* - Disassembly

## Module 4
* you can select code in either the listing view or decompiler view to highlight it, to make the highlight permanent, right-click > select "Program highlight"
* `command key/windows key + select a mnemonic (instruction)`
in listing window will highlight every instance of that mnemonic
* you can add annotations that link to external projects, URLs, or simply adding comments + more in the code browser
* use the data type manager window to select the type you want to apply, it's as simple as dragging & dropping the data type to the location you want to apply it in (whether that be in the listing or decompiler)
* function call graph shows function calls from current function **window > function call graph**
* function call tree depicts a hierarchical relationship of function calls
* the symbol tree allows for exploration of imports, exports & functions
* Ghidra also allows for managing external programs, which means you can add additional programs (libraries such as user32.dll, etc) the program depends on, you'd need to add these libraries to your project
* functions can be created, and edited. Editing includes changing: parameter types, calling conventions, undefining functions, etc
# ![](/home/n9/study/cybernotes/functionediting.png) 
* symbols can be added, usually in the form of PDB files, but with malware this is rare but when working with programs that rely on Microsoft code this can help identify when calls to Microsoft libraries are made within the program

## Module 5
* clear code bytes can be used to convert disassembled code to raw data
* after patching an instruction, you should **right click > select clear flow & repair** in order to go back through the program & analyze it again
* headless mode is located at **ghidra_install\support\analyzeHeadless.(sh|bat)** along w/documentation (including use cases) in **analyzeHeadlessREADME.html**
* with headless mode, you can import & analyze programs in bulk
* Ghidra comes preloaded with tons of scripts & you can write your own scripts, view them in the script manager 