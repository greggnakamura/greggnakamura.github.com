---
layout: post
title: Setting up Jekyll on Windows
tags: 
- jekyll 
---

Jekyll is not fully supported on Windows and **setting it up can be a bit of a challenge to a Ruby novice, such as myself**. These processes have been documented a few times already, but I thought it wouldn't hurt to share my experiences here.  I found this post by [Yi Zeng](http://yizeng.me/2013/05/10/setup-jekyll-on-windows/) to be quite good, but here are some others I used as well:

- [Converting my old blog](http://blog.davidebbo.com/2014/01/converting-my-old-blog.html) - Dave Ebbo
- [How to install Jekyll on Windows](http://minimaldev.com/how-to-install-jekyll-on-windows/)
- [Getting Jekyll up and running on Windows](http://thedustytome.com/2014/02/15/Getting-Jekyll-up-and-running-on-Windows/) - Nate Sauber

## "Get up and running...in seconds?" ##
So, my challenge started pretty much from the get-go. Jekyll's first instructions are to run 'gem install jekyll'.  Simple enough, right?  Well...

    > gem install jekyll
    
    ERROR:  Error installing jekyll: The 'fast-stemmer' native gem requires installed build tools.
    Please update your PATH to include build tools or download the DevKit from 'http://rubyinstaller.org/downloads' and follow the instructions at 'http://github.com/oneclick/rubyinstaller/wiki/Development-Kit'

This is where I turned to [Yi Zeng's post](http://yizeng.me/2013/05/10/setup-jekyll-on-windows/) for help. Basically, all I really needed to do was [install DevKit](http://rubyinstaller.org/downloads/) and then updated the '[config.yml](http://stackoverflow.com/questions/20810653/how-do-i-configure-config-yml-so-that-i-can-install-devkit)' file.  

After installing DevKit I was able to run the 'init' command successfully:

	> ruby dk.rb init
    
    Initialization complete! Please review and modify the auto-generated
    'config.yml' file to ensure it contains the root directories to all
    of the installed Rubies you want enhanced by the DevKit.

But then, if you update the 'config.yml' file incorrectly, as I did, you will see this message when attempting to run 'ruby dk.rb install':

    C:\Users\Gregg\Downloads> ruby dk.rb install
    Invalid configuration or no Rubies listed. Please fix 'config.yml'
    and rerun 'ruby dk.rb install'

My correct entry was '- C:\ruby200'. For further details on this or Environmental Path Variable issues, please review the accepted answer here: [http://stackoverflow.com/questions/10694997/gem-install-json-v-1-7-3-gives-please-update-your-path-to-include-build-tools](http://stackoverflow.com/questions/10694997/gem-install-json-v-1-7-3-gives-please-update-your-path-to-include-build-tools)

Once all of the above was resolved, I was able to run the install:

    > ruby dk.rb install
    
    [INFO] Updating convenience notice gem override for 'C:/ruby200'
    [INFO] Installing 'C:/ruby200/lib/ruby/site_ruby/devkit.rb'

Success! From this point, I was able to install Jekyll, Pygments, Python, Easy Install, then start Jekyll.

**One thing to note with Python and RubyGems**. Both will need their Environmental 'Path' Variables added (*Python, Python Scripts, & RubyGems*).  For RubyGems, make sure that you have not installed this within you 'User' directory. This is a restricted directory.  For further details on this, please see the [accepted answer here](http://stackoverflow.com/questions/17550903/why-do-i-get-a-permission-denied-error-while-installing-a-gem).