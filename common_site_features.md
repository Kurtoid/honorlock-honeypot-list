## TODO: update for 2nd gen sites


# Techniques for finding HL Honeypots
## for version 2 sites
Until a few days ago (27/3/2021), all of the new sites had `noindex,nofollow` set on all of them. As of today, it looks like the sites are now indexable by search engines!

A simple query targeting their privacy policy (I know, they listened!) seems to work: `"complaints directly to us at privacy@hlprivacy.com"`. I'm using the privacy policy as it seems to be constant between sites - the front matter is different for each site.

Other observations: Remember the `battlemedialab` account that appeared in `wpscan` on the v1 sites? We know now where they come in: they write the front matter on the v2 sites.

## old, for v1 sites
* use questions posted on existing known sites
* non-english questions work best
* look for simple site names like buzzfolder or studyeffect
* use a search thumbnail extension to quickly screen potential sites
* if down, check archive.org and add to old-sites.txt
* Use Google searches targeting their Ghost plugin (such as [this one](https://www.google.com/search?q=%22ghost+init%22+%22Audiocast%22&hl=en&filter=0&biw=1536&bih=760))

# common features
* simple, two-word URLs
* no logo; text-only wordmark
* home/index page has some variant of "Hello, this website is under construction. If you have any questions, please contact the system administrator."
* question posts will have two buttons, usually "SHOW ANSWER" and "HIDE ANSWER"
* SSL uses LetsEncrypt
* Posts often have an associated hash, which can be seen in the [OpenGraph](https://ogp.me/) meta tags in `<head>`.
* Active: Registered from [Google Domians](https://www.whois.com/whois/quizlookup.com) using a privacy-protection service

## TODO: screenshots

# common page scripts
* body usually starts with two <audio /> tags
* adds "onClick" listener to *all* buttons to play some audio
* loads inspectlet
* adds js call ghostConsole() to add invisible text to page. I'm guessing this is for inspectlet to capture

# scratch notes
XPath for "real" question: `//div[@class="panel-heading" and not(contains(text(),"–"))]`
