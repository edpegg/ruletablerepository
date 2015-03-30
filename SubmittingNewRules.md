<p align='right'><a href='http://code.google.com/p/ruletablerepository/source/list?path=/wiki/SubmittingNewRules.wiki'>detailed page changes</a></p>

## Before submitting ##

It's always a good idea to get some feedback before presenting your rule to the world as finished work. Good places to do this are:

  * http://www.conwaylife.com/forums/ - you can attach your rule to a forum post.
  * The Golly mailing list: [golly-test@lists.sourceforge.net](mailto:golly-test@lists.sourceforge.net) ([archives](https://sourceforge.net/mailarchive/forum.php?forum_name=golly-test))

## Submission procedure ##

Either:
> <b>Join this project.</b> Email one of the owners with your Google Account email address to become a project member. You can then add your rules and descriptions and so on.
Or:
> <b>Email</b> your contribution to one of the project members (e.g. [tim.hutton@gmail.com](mailto:tim.hutton@gmail.com)). Put together a zip file as described below.

## Will they be accepted? ##

Yes! This is a community project, so anything of interest to the community should be included. If we all work in public then we all get the benefit of cross-fertilizing each others' ideas.

## What to send ##

Ideally, the rule should be presented in a ZIP compressed archive, containing:

  * The transition file(s) (.table or .tree) containing comments that describe the states and the transitions.
  * Display files as needed (.colors, .icons).
  * Several sample patterns (.rle, .mc, etc.) to demonstrate key features; these sample files should contain explanatory comments.
  * A brief description of the rule, including the person who invented it and so on, so we can add some text to TheRules.

Golly can now open zip files directly, so it's easy to check that your zip file works.

If your rule table is extremely good or a classic of the literature, please consider submitting it to the Golly project instead, and we'll link to it from here. The Rule Table Repository is more of a community sharing area so has a lower standard of acceptance.

## Rule naming conventions ##

When naming a .table or .tree file please follow these conventions:

  * Capitalize all rule names and create files like Foo.table rather than foo.table.  This helps to emphasize that rule names are important, especially on case-sensitive file systems.  If the rule "foo" is specified inside a .rle or .mc file then Golly won't be able to find Foo.table on a case-sensitive system like Linux.
  * To allow for possible future extensions in the way Golly handles rule names, it's best to use only letters and digits (and possibly hyphens -- see the next item).  Note in particular that spaces must not be used.
  * If you have a number of closely related rules then you might want to start each name with the same prefix followed by a hyphen and a unique suffix. All such rules can then share a single .colors and/or .icons file that uses the same prefix.  For example, Foo-1.table and Foo-2.table can share Foo.colors and Foo.icons (but if Foo-1.colors also exists then that file takes precedence for the Foo-1 rule).

## Everything here is free ##

Please bear in mind that all content in this repository is available to the public for free for any purpose. Our source code is available under the GPL license, while the rule tables and so on are all essentially under a public domain license. Please don't submit files that contain other license claims - don't assert copyright on your creations for example. In general the community tries to be very careful to correctly attribute credit but if you're not happy with this rule then don't submit your stuff.

## Editing TheRules page ##

If you're a project member you can edit TheRules directly to add your contribution. Some things to bear in mind:

  * Please make sure that the GollyAccessPoint is maintained in sync. The page looks wrong in the wiki but this is deliberate - the content is actually meant for access from Golly (Help menu | Online Archives) and looks fine there.
  * Please upload your zip files to the file download area so that they are stored here. Currently we link to some files stored elsewhere but this runs the risk of broken links in future.