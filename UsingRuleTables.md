## 1. Use them in Golly: ##

The rule table format started with [Golly](http://golly.sourceforge.net)'s need to support different CA. Golly is distributed with many of these rule tables already included, so just explore the example patterns to see them in action.

Or, for new .table files:
  1. Save the .table file into your rules folder (set in `Preferences | Control`).
  1. Use `Control | Set Rule...` to change to the new rule.

Golly also accepts _rule tree_ files, which are hard for humans to read and author but simple for programs to utilise since they map directly onto a lookup function. More details [here](http://golly.sourceforge.net/Help/formats.html#tree). Golly comes with a utility ([RuleTableToTree](http://golly.cvs.sourceforge.net/viewvc/golly/golly/src/Scripts/Python/Rule-Generators/RuleTableToTree.py?view=markup)) to convert a rule table into a rule tree. Rule trees only support the von Neumann and Moore neighborhoods at the moment. Note that rule trees are not really meant to be authored directly -- the easiest way to create a new .tree file is to use the [make-ruletree.py](http://ruletablerepository.googlecode.com/files/make-ruletree.py) script (see the comments at the top of the script).

## 2. Use them in your own programs: ##
  * C++: Download or browse the source code [here](http://code.google.com/p/ruletablerepository/source/browse/trunk/src). As an example, [read\_ruletable.cpp](http://code.google.com/p/ruletablerepository/source/browse/trunk/src/read_ruletable.cpp) shows how to use the ruletable class to read CA rule tables in your own project.
  * Python: Use [ReadRuleTable.py](http://golly.cvs.sourceforge.net/viewvc/golly/golly/src/Scripts/Python/glife/ReadRuleTable.py?view=markup) in your Python project. Strip out the golly bits.

## 3. Export them from other programs: ##

[make-ruletable.cpp](http://code.google.com/p/ruletablerepository/source/browse/trunk/src/make-ruletable.cpp) shows how to create rule table files if you have an existing CA implementation you want to convert. It's only in C++ at the moment but could be adapted for other languages.