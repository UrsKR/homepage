---
layout: post
title:  Converting hg to git on Windows
date:   2011-09-06 18:06:00 +0200
categories: technical infrastructure git mercurial windows
---
Converting from hg/mercurial to git is really straightforward.  
To start with, all I had was this instructional [post](https://hedonismbot.wordpress.com/2008/10/16/hg-fast-export-convert-mercurial-repositories-to-git-repositories/). Sounds really easy and would not merit a post of it's own, if it wasn't for a [bug in MSysGit](http://groups.google.com/group/msysgit/tree/browse_frm/month/2008-04/ab5a9c7a7e23d4c5?rnum=51&_done=/group/msysgit/browse_frm/month/2008-04?fwc%3D2%26&pli=1).  
Here's what I did to work around:  
1. Download the latest version of Ubuntu.
2. Burn it on a CD.
3. Reboot from the CD, using "Live CD" mode.
4. Install git via the "Synaptic Package Manager"
5. Still in the "Synaptic Package Manager", activate the "universe"-repository and install mercurial.
6. Mount my hard drive so I have access to the hg's working copy.
7. Follow the [instructions](http://hedonismbot.wordpress.com/2008/10/16/hg-fast-export-convert-mercurial-repositories-to-git-repositories/) from the post - but do everything in the user home.
8. Finally, copy the resulting repository onto my harddrive
9. Reboot into Windows.  
    
The converted result looks like [this](https://github.com/Butatopanto/Butatopanto/tree/4dbc0dc07011ce1e6438c9efd1a755914145b73e).  
**Edit**: Rob Rutherford [suggests](https://plus.google.com/100051405258786750070/posts/EkgbX3ftko6) using [Virtual Box](http://www.virtualbox.org/) and your [personal flavor of Linux](http://virtualboxes.org/) for a more persistent solution.  
**Edit 2**: Or just boot Virtual Box with the ISO image I linked to above.