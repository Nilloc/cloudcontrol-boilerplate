This is a boilerplate for users who want to get a hello world app running on cloudcontrol.com (PHP cloud hosting similar to Heroku)

More to come.

    $ sudo easy_install cctrl

XCode4 users on Intel Mac prepend 

    $ sudo env ARCHFLAGS="-arch i386 -arch x86_64" easy_install cctrl

Then add your public key for committing/delpoyment

    $ cctrluser key.add

Switch to your local Git branch

    $ cd YOUR_LOCAL_BRANCH
    $ cctrlapp APP_NAME create php
    $ cctrlapp APP_NAME/default addon.add mysql.free
    $ cctrlapp APP_NAME/default addon mysql.free
    
The credentials for your new mysql db will be output on the command line, add them to your app if it exists, or save them somewhere secure.

When your app is ready, and changes are committed, push it to cloudcontrol and deloy it.    
    
    $ cctrlapp APP_NAME/default push
    $ cctrlapp APP_NAME/default deploy
    $ open http://APP_NAME.cloudcontrolled.com