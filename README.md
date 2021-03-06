# Learn AppleScript

Notes & code pieces recorded during my exploration to AppleScript.


## Snippets


### Strike keys in any situation

```applescript
tell application "System Events"
    -- Strike a return key
    keystroke return

    -- Strike ⌘ + C
   keystroke "c" using command down
end tell
```

### Open url in Safari

```applescript
tell application "Safari"
    -- `activate` will bring Safari to front, could be removed otherwise
    activate

    -- Open url in current tab
    set URL of document 1 to "https://www.baidu.com/s?word=a"
end tell
```

### Open url scheme in any application

```applescript
tell application "Spotify"
    activate
    open location "spotify:search:hello"
end tell
```

### Set clipboard to a variable

```applescript
set myvar to the clipboard
```

### Display dialog & alert

```applescript
display dialog myvar
```

### Url encode a variable

```applescript
set cmd to "python -c 'import urllib, sys; print urllib.quote(sys.argv[1])'" & " " & quoted form of selected
set encoded to do shell script cmd
```

### Tell current application

```applescript
tell application (path to frontmost application as text)
    ...
end tell
```

### Delay for seconds

```applescript
-- Delay for 1s
delay 1

-- Decimal is OK
delay 0.5
```

### Copy image to clipboard

```applescript
set the clipboard to (read "image.png" as TIFF picture)
```

### Concat strings

```applescript
set a to "Al "
set b to "was "
set c to "here."
set myVar to a & b & c
display dialog myVar
```


## Resources

https://en.wikibooks.org/wiki/AppleScript_Programming
