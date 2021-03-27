How do Honorlock's honeypot sites actually work? This repo contains efforts to find and list Honorlock honeypot domains. Since we don't know how many there are, these lists are probably far from complete.

`live-sites.txt` lists.. well... live sites.

`live-sites-blocklist` is an uBlock list you can import.
* instructions at https://github.com/gorhill/uBlock/wiki/Filter-lists-from-around-the-web.
* use `https://raw.githubusercontent.com/Kurtoid/honorlock-honeypot-list/main/live-sites-blocklist` as the list address

`old-sites.txt` contains sites that used to host HL honeypots, but don't now.

`common_site_features.md` contains [common features and techniques](https://github.com/Kurtoid/honorlock-honeypot-list/blob/main/common_site_features.md)


Don't cheat, folks.

# Techniques for finding HL Honeypots
Until a few days ago (27/3/2021), all of the new sites had `noindex,nofollow` set on all of them. As of today, it looks like the sites are now indexable by search engines!

A simple query targeting their privacy policy (they listened!) seems to work: `"complaints directly to us at privacy@hlprivacy.com"`. I'm using the privacy policy as it seems to be constant between sites - the front matter is different for each site.

The v2 sites don't appear to use Quizlet sets as filler - it looks like it's only 'used' questions (although I should verify further). The v2 sites also use their character swapping on _all_ questions (the v1 sites only swapped characters on real questions, which is how the scraper script detected them). v2 sites also have different internal structure - questions are stored via custom post metadata, **and are retrievable via the Wordpress JSON API!!!** [Demo here](https://wikicram.com/wp-json/wp/v2/posts/1051504)

Other observations: 
Remember the `battlemedialab` account that appeared in `wpscan` on the v1 sites? We know now where they come in: they write the front matter on the v2 sites.

Looks like our uBlock submission worked: only sites that I _didn't_ submit got upgraded to v2 (which is why it took me so long to notice them), so thats cool. I'm probably not going to submit them to uBlock, as my entire grounds for doing so was the absence of a privacy policy, which the v2 sites now have.

Also, if you're reading this: Hello Honorlock!

## on the v1 sites
This file originally contained instructions/info on their v1 sites - I'm removing it to keep this file clean - find the old text in the git commit history.