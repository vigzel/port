# port.js

port.js is an expanded version of
[Michael Gundlach’s Chrome-(and-Opera<em>!</em>)–to–Safari porting library for extensions](https://adblockforchrome.googlecode.com/svn/trunk/port.js).

## Dev HOWTO

Add as the first script to your Safari plist file (created by the Extension
Builder) and your Chrome and Opera manifest files, background pages, and options
pages.

Additional modifications for EDGE: 
 * The manifest file needs one additional key:
     "minimum_edge_version": "33.14349.1000.0"
 * You need to set additional permissions on extension directory. Create a .cmd 
   file with this line and run it from inside the extension directory:<br/>
     icacls %CD% /grant "*S-1-15-2-3624051433-2125758914-1423191267-1740899205-1073925389-3782572162-737981194":"(OI)(CI)(WDAC,WO,GE)"  

Then use `chrome.*` APIs as usual and check the global `SAFARI` and `EDGE` boolean for
doing browser-specific stuff. The `safari.*` APIs will still be available in
Safari and the `chrome.*` APIs unchanged in Chrome and Opera.


## License

Copyright 2010–2012 Michael Gundlach  
Copyright 2012, 2013 Disconnect, Inc.

This program is free software: you can redistribute it and/or modify it under
the terms of the GNU General Public License as published by the Free Software
Foundation, either version 3 of the License, or (at your option) any later
version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY
WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A
PARTICULAR PURPOSE. See the
[GNU General Public License](https://www.gnu.org/licenses/gpl.html) for more
details.
