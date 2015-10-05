Running and Building Ghost
==========================

When this repo has been cloned, we need to add the jamiehill.github.io submodule, which effectively houses the static content for Github Pages.

Add the Submodule
-----------------

From project root, add the github pages repo as a submodule, in the folder `static`, and initialize it :

    git submodule add https://github.com/jamiehill/jamiehill.github.com.git static
    git submodule init
    git submodule update
    
Modify your Blog
----------------

That's pretty much all we need to do.  We can now start our local instance of Ghost:

    npm start
    
And login in to the admin panel to configure for the first time:

    http://localhost:2368/ghost
    
When any changes are made to your blog, be they theme mofications, css updated, or edit/creating new pages, the stat needs to be generated again, into the static version that Github Pages can host.

All published blog posts will be exported to the static folder with Buster.  The following commands are the one's for you:

    buster generate --domain=http://localhost:2368
    buster preview

The first line will simply generate our files for us, while the second, serve up what's been generated, on `localhost:9000`. This is optional, if you want to preview whats been generated

If you're happy with you results, simply commit everything in you submodule, et Voila!