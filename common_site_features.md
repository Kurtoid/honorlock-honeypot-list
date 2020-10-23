# Techniques for finding HL Honeypots
* use questions posted on existing known sites
* non-english questions work best
* look for simple site names like buzzfolder or studyeffect
* use a search thumbnail extension to quickly screen potential sites
* if down, check archive.org and add to old-sites.txt


# common features
* simple, two-word URLs
* no logo; text-only wordmark
* home/index page has some variant of "Hello, this website is under construction. If you have any questions, please contact the system administrator."
* question posts will have two buttons, usually "SHOW ANSWER" and "HIDE ANSWER
* SSL uses LetsEncrypt

## TODO: screenshots

# common page scripts
* body usually starts with two <audio /> tags
* adds "onClick" listener to buttons to play some audio
* loads inspectlet
