# Bash

## Commands

* **`pwd`** writes the *absolute pathname* of the current _working directory_ to the standard output.
* **`showrgb`** displays an rgb color-name database
* C++:
  * **`clang++ -std=c++11 -stdlib=libc++ example.cpp -o example_program`**
* VIM:
  * **`i`** INSERT
  * **`:w`** write
  * **`:wq`** write and quit
  * **`:x`** write and exit
* ***Pipe:*** **`command_a | command_b`** runs *command_b* with the input as the output of *command_a*, (e.g. `cat example.txt | sort` prints the sorted output of example.txt)
* **`<command> &`** runs command in background
  * **`jobs`** lists all jobs running in background

  * **`nice <command>`** runs command in background at lower priority
* **`diff doc_1 doc_2`** outputs the differences between *doc_1* and *doc_2*
* **`fc`** *fix command* - Preview, edit and run old commands easily. With no arguments- loads the editor with the most recent command. **`fc`** actually runs the commands after you edit them
  * **`fc -l`** option lists previous commands. With no arguments, lists last 16 commands
  * **`fc -n`** suppresses the line numbers
  * **`fc -e`** quick edit. An "escape hatch" from editors like *vi* or *emacs*
  * *bash* also has the built-in command **`history`**
* History expansion
  * Event designators
      * **`!!`** refers to the last command (and re-runs it)
      * **`!241`** refers to the command number *241*
      * **`!-3`** runs the current command line minus *3* (basically the command ran three commands ago)
      * **`!string`** runs the last command starting with *string*
      * **`^misspelled^correct`** replaces the *misspelled* word in the last command with the *correct* spelling, then runs it.
  * Word designators
      * the word designator follows the event designator. (e.g. you could re-run the previous command with different arguments by passing in `!!:0` followed by the new arguments
      * **`0`** the zeroth (first) word in a line
      * **`n`** the nth word in a line
      * **`^`** the first argument (the second word)
      * **`$`** the last argument in a line
      * **`*`** all words but the zeroth (synonimous with **`1-$`**)
  * Modifiers
	   * The modifiers follow the word designatorm if there is one
	   * **`p`** prints the resulting command but doesn't execute it
	   * ...



## Control keys

* **CTRL-Z** - *susp* - Suspend current command
* **CTRL-C** - *intr* - Stop current command 
* **CTRL-M** - RETURN
* **CTRL-?** - DELETE
* **CTRL-D** - *eof* - End of input
* **CTRL-U** - Erase entire line
* ...
* **`stty all`** - lists all control-key settings

## Learning

* Shell  - macro processor that executes commands (macro processor means functionality where text and symbols are expanded to create larger expressions). I\O Interface for an OS like UNIX. 

  * Bash - Bourne Again Shell. The shell, or command language interpreter for the GNU operating system.
  * Unix shell - both command interpreter and programming language. 
  * A shell can be used interactively (user input) or non-interactively (commands read from a file).
  * Provides a set of built-in commands (builtins) (cd, break, continue, exec)
  * Has an embedded programming language. Like all high-level language, the shell provides variables, flow control constructs, quoting and functions.

* GNU (GNU’s Not Unix) - Unix-like operating system.

  * The program that allocates machine resources and talks to the hardware is called a “kernel”.
  * GNU is typically used with the Linux kernel. Hence why the typical combination GNU/Linux operating system.
