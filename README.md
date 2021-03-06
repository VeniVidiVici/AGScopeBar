# AGScopeBar
=============

AGScopeBar is a modern implementation of a "scope bar" in OS X UI
terms. A scope bar is composed of one or more groups of items, where
each item is a button or popup menu. The buttons within a group can
be momentary "normal" push buttons, or have a selection mode with
zero or more selected, one or more selected, or always only one.
The right side of the scope bar can also have an accessory view.


## Why not MGScopeBar?

MGScopeBar, a similar project by Matt Gemmell, has been around for
years, but a number of things bugged me about it so wrote this. The
feature set isn't massively different, but there are enough small
changes and a much cleaner API.

Among the small differences I wanted from MGScopeBar which are noted
in the screenshot below:

1) Buttons icons use the new inset look versus being flat gray.
2) Button titles also use the inset look versus being flat black.
3) When a group collapses into a single popup due to space constraints,
it doesn't have a big selected background, and fits to the title width.
4) AGScopeBar allows the selection mode where one or more items can
be selected, while MGScopeBar does not.

![Screenshot](https://github.com/swillits/AGScopeBar/raw/master/Docs/Screenshot.png)


Furthermore, the AGScopeBar API is much sleeker, while being richer.
The entirety of MGScopeBar's configuration is done through delegate
methods which I find overly verbose, and in my experience thanks to
reloadData reloading *everything* it got me into a very noticeable
performance problem that was a nuisance to work around. (Long story).
AGScopeBar doesn't have a "reload" metaphor — you simply modify the
one thing you want to change directly.


![Screenshot](https://github.com/swillits/AGScopeBar/raw/master/Docs/Screenshot2.png)

Which would you rather write?



Usage
=============
There are three classes in this project: AGScopeBar is a custom NSView
which contains a collection of AGScopeBarGroups. Each group contains a
collection of AGScopeBarItems which are the buttons and popups in the
bar. Properties on all three classes allow you to tweak appearance,
selection behavior, behavior during resizing, 

Button selection (clicks and on/off) are funelled through the single
delegate method:

 - (void)scopeBar:(AGScopeBar *)theScopeBar item:(AGScopeBarItem *)item wasSelected:(BOOL)selected;

See the AGScopeBar header for everything.



Requirements
=============
- OS X 10.6
- Runs in 32 or 64 bit.


License
=============
Code-level attribution should be maintained, but no credit
visible to the end-user is necessary.


--

Seth Willits
http://www.araelium.com/
