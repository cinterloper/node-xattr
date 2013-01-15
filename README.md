#node-xattr

node-xattr is a native module wrapping xattr to read and set extended attributes on files. 

## Build

node-waf configure && node-waf build && node-waf install

## usage

  var xattr = require("xattr");

Get all the extended attributes on a file, returns obj 
 
  var attrs = xattr.glist("/path/to/file");

Get just the extended attribute names on a file, returns array obj 
 
  var attrs = xattr.clist("/path/to/file");

Set an extended attribute on a file.  Note at thie moment you can only set string values.
  
  xattr.set("/path/to/file", "someAttribute", "someValue");

Remove xattr on a file, returns bool
 
  xattr.remove("/path/to/file", "user.attribute");

xattr.list defaults to xattr.glist, however you can change this by calling xattr.ccompat(true)
 
