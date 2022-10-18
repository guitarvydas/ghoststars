# ghoststars

Transpile a DSL to JSON.  The DSL is for a dungeon-like game.

# Usage
run
> make
to get the fmt-js repos and npm stuff
(Note that fmt-js is its own repo and including it as a subdirectory here does not include fmt-js in a 'git push' of this ghoststars repo)

load `demo.html` into a browser
press

# What?
Transpiles this script into JSON...
```
❖ Show prolog_bg at 0x-550. Move prolog_bg to 0x0
over 300 frames. Wait 150 frames.

		    CHEL:NA
	  The last time I saw
	  her... She was smiling. As
	  if she had some secret that
	  she couldn't wait to tell me.
	  
	  And then, in a sudden wash of
	  red, she was gone.
	  
	  Gone as if she had never stood
	  beneath the uncaring stars.

❖ Fade to black over 40 frames. Jump INTRO.
```
becomes
```

{ onenter:
  [
      ["image","prolog_bg",0,-550],
      ["moveto","prolog_bg","???",0,0300,"easin"],
      ["wait",150],

      
      ["say","CHEL:NA","The last time I saw
	  her... She was smiling. As
	  if she had some secret that
	  she couldn't wait to tell me.
	  
	  And then, in a sudden wash of
	  red, she was gone.
	  
	  Gone as if she had never stood
	  beneath the uncaring stars.

"],
      ["fadeout",40],
      ["jump","INTRO"],
      true]
}
```
# What to Look At..
The pattern-matching spec is in `ghost_stars.ohm`.

The code fabrication spec is in `ghost_stars.fmt`.

# History
Earlier versions of this code also produced Lisp and an identity parse.