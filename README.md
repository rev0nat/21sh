# 21sh
  After minishell, welcome 21sh

## DOWNLOAD
  $> git clone https://github.com/rev0nat/21sh.git dir_name
 
## PREREQUISITES
  To be able to compile and run this program, you'll need the folowing:
  - A terminal emulator such as xterm or iterm;
  - Clang at any recent version; (mine is clang-900.0.39.2 -- Apple modified)

## COMPILATION
  Makefile rules:
  - $> make
      Compiles the project using the 'all' rule
  - $> make clean
      Removes all .o && .d
  - $> make fclean
      Same as 'clean' but removes the executable also
  <! Bear in mind that this project was developped under MacOs Sierra 10.12.6.
  Some features might not work if you are using another environment.
  For example the -ltermcaps Library option doesn't work on Linux and has to be replaced by -lncurses in order to compile !>
  
## RUN
  $> ./21sh
  
## FEATURES
### Line editing with the termcaps library
  - Right|Left arrow to move cursor
  - Del|Suppr to delete characters
  - Up|Down arrow to browse through history (shell will create a ~/.21sh_history file if you don't have one. If you do, we're flattered)
  - ^b|^f will move cursor to previous or next word
  - Home|End will move cursor to beginning/end of line
  - ^r will allow you to search for a specific command in history
  - ^c will copy the word at current cursor position
  - ^a will copy the all line
  - ^p will paste what's in copy_buffer to your line at cursor position
  - ^c will send an SIGINT to your line
  We also manage UTF-8 Unicode in our shell. Try it out!
### Redirections and FileDescriptor aggregating
  - Our shell manages redirections:
    ```diff
    $> echo 1 >out >&2 2>err
    + Try it out!
    ```
  - fd aggregating:
    ```diff
    $> cat abc 2<&-
    + Try it out!
    ```
  - pipes:
    ```diff
    $> ls ./ > testfile ; cat testfile | grep a | tail -n1
    + Try it out!
    ```
Have fun trying out our home made shell!
