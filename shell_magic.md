# Shell magic

### Tr
[https://www.geeksforgeeks.org/tr-command-in-unix-linux-with-examples/](https://www.geeksforgeeks.org/tr-command-in-unix-linux-with-examples/!)

```
Syntax : 
tr [OPTION] SET1 [SET2]

-c : complements the set of characters in string.i.e., operations apply to characters not in the given set
-d : delete characters in the first set from the output.
-s : replaces repeated characters listed in the set1 with single occurrence
-t : truncates set1
```

```sh
# Transform lowercase to uppercase
cat greekfile | tr “[a-z]” “[A-Z]”
cat geekfile | tr “[:lower:]” “[:upper:]”

echo "Welcome To GeeksforGeeks" | tr [:space:] '\t'

# Replace curly brackets with round brackets
tr '{}' '()'  newfile.txt

# Squeeze - Useful for converting whitespaces to single spaces
echo "Welcome    To    GeeksforGeeks" | tr -s [:space:] ' '

# Delete
echo "my ID is 73535" | tr -d [:digit:]

# -c option complements a set, so tis will delete everything not a digit
echo "my ID is 73535" | tr -cd [:digit:]
```

### Cut
[https://www.geeksforgeeks.org/cut-command-linux-examples/?ref=lbp](https://www.geeksforgeeks.org/cut-command-linux-examples/?ref=lbp!)

### Paste
Join lines by a separator
'''sh
paste -sd "," file.txt
'''


### Sed
[https://www.geeksforgeeks.org/sed-command-in-linux-unix-with-examples/?ref=rp](https://www.geeksforgeeks.org/sed-command-in-linux-unix-with-examples/?ref=rp!)

The all powerfull stream editor

```sh
#subsitute, use -E for extrended regular expressions and group capture, use \ as escape character
# Captured groups can be refered by \1,\2.. or & for the whole matched pattern
sed -E "s/(.*)/\'&\'/"

```



### alias
Add alias to bash_profile


### Vi

`:%3,5!python -m json.tool` Convert range (3,5) to pretty print json


### History
`!$` expands to the last word of previous command in history


# Vi & other Command line tools
- [ ] Setup fuzzy finding tools with fzf ([link](https://www.youtube.com/watch?v=QeJkAs_PEQQ!))
- [ ] Working with multiple files ([link](https://blog.confirm.ch/mastering-vim-working-with-multiple-files/!))
- [ ] The ultimate vim configuration ([link])(https://github.com/amix/vimrc!)

#### Reference
- A  =  Append to a line
- :e  = Editor (open a new file). Press Ctrl-D after :e to show file options
- :tabe = Open file in new tab
- :tabc = Close tab
- :sp = split tab horizontally
- :vsplit = split tab vertically
- Ctrl-w + <Navigation keys> = Switch focus between tabs
- G = Move to end of file
- o = Add new line below & enter insert mode
- p = Add new line below
- d = Cut selection, selection can be made by visual mode or using any range
- y = Yank, vim terminology for copy
- b = Go back a word
- gg = Go to top of file
- gt = Switch to next tab
