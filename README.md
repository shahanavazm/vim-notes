# vim-notes

## copy and paste
use the following setting in vimrc to enable easy copy and paste between vim and other applications.  
set clipboard=unnamedplus  
autocmd TerminalWinOpen * set clipboard=unnamedplus  
  
with this setting in place, the following will happen:  
when deleting with d, c, x or s, content is copied to registers " and +.  
when yanking with y, content is copied to registers ", + and 0.  
when pasting with p or P, content is pasted from register +.  
when pasting in insert mode, try to use ctrl r +.  
to paste from yank register (register 0) use "0p or "0P or ctrl r 0.  
so in summary consider + as the default register and 0 as the yank register.  
frequently we need to copy a text to yank register and then clear it, then use: ygvc  

## vim operator noun grammer:
operator ( motion | text-object )  
operator = ["register] [repetition] ( d | c | y ...)  
motion   = [repetition] ( h | l | j | k | w | b | /text | ?text | \`a ...)   
text-object = [repetition] modifer object  
modifier = a | i  
object = w | W | p | s | ( | ) | { | } | [ | ] | " | ' | \`   
  
examples:  
"02d2/text  
"02d2aw  

