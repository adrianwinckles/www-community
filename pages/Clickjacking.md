---

title: Clickjacking
layout: col-sidebar
author:
contributors:
auto-migrated: 1
permalink: /Clickjacking

---

Clickjacking, also known as a "UI redress attack", is when an attacker
uses multiple transparent or opaque layers to trick a user into clicking
on a button or link on another page when they were intending to click on
the the top level page. Thus, the attacker is "hijacking" clicks meant
for their page and routing them to another page, most likely owned by
another application, domain, or both.

Using a similar technique, keystrokes can also be hijacked. With a
carefully crafted combination of stylesheets, iframes, and text boxes, a
user can be led to believe they are typing in the password to their
email or bank account, but are instead typing into an invisible frame
controlled by the attacker.

# Examples

For example, imagine an attacker who builds a web site that has a button
on it that says "click here for a free iPod". However, on top of that
web page, the attacker has loaded an iframe with your mail account, and
lined up exactly the "delete all messages" button directly on top of the
"free iPod" button. The victim tries to click on the "free iPod" button
but instead actually clicked on the invisible "delete all messages"
button. In essence, the attacker has "hijacked" the user's click, hence
the name "Clickjacking".

One of the most notorious examples of Clickjacking was an attack against
the [Adobe Flash plugin settings
page](http://www.macromedia.com/support/documentation/en/flashplayer/help/settings_manager06.html).
By loading this page into an invisible iframe, an attacker could trick a
user into altering the security settings of Flash, giving permission for
any Flash animation to utilize the computer's microphone and camera.

Clickjacking also made the news in the form of a [Twitter
worm](http://shiflett.org/blog/2009/feb/twitter-dont-click-exploit).
This clickjacking attack convinced users to click on a button which
caused them to re-tweet the location of the malicious page, and
propagated massively.

There have also been clickjacking attacks abusing Facebook's "Like"
functionality. [Attackers can trick logged-in Facebook users to
arbitrarily like fan pages, links, groups,
etc](http://threatpost.com/en_us/blogs/facebook-jacking-scams-expand-060310)

# Defending against Clickjacking

There are two main ways to prevent clickjacking:

1.  Sending the proper Content Security Policy (CSP) frame-ancestors
    directive response headers that instruct the browser to not allow
    framing from other domains. (This replaces the older X-Frame-Options
    HTTP headers.)
2.  Employing defensive code in the UI to ensure that the current frame
    is the most top level window

For more information on Clickjacking defense, please see the the
[Clickjacking Defense Cheat
Sheet](Clickjacking_Defense_Cheat_Sheet "wikilink").

# References

  - [Why am I anxious about
    Clickjacking?](https://www.linkedin.com/pulse/20141202104842-120953718-why-am-i-anxious-about-clickjacking)

<!-- end list -->

  -
    A Basic understanding of Clickjacking Attack

<!-- end list -->

  - <https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/frame-ancestors>

<!-- end list -->

  -
    Mozilla developer resource on Content-Security-Policy
    frame-ancestors response header.

<!-- end list -->

  - <https://developer.mozilla.org/en-US/docs/The_X-FRAME-OPTIONS_response_header>

<!-- end list -->

  -
    Mozilla developer resource on the X-Frame-Options response header.

<!-- end list -->

  - [Busting Frame Busting: A study of clickjacking vulnerabilites on
    top sites](http://w2spconf.com/2010/papers/p27.pdf)

<!-- end list -->

  -
    A study by the Stanford Web Security Group outlining problems with
    deployed frame busting code.

<!-- end list -->

  - [Clickjacking, Sec
    Theory](http://www.sectheory.com/clickjacking.htm)

<!-- end list -->

  -
    A paper by Robert Hansen defining the term, its implications against
    Flash at the time of writing, and a disclosure timeline.

<!-- end list -->

  - <https://www.codemagi.com/blog/post/194>

<!-- end list -->

  -
    Framebreaking defense for legacy browsers that do not support
    X-Frame-Option headers.

<!-- end list -->

  - [Anti-clickjacking J2EE
    filter](ClickjackFilter_for_Java_EE "wikilink")

<!-- end list -->

  -
    A simple J2EE servlet filter that sends anti-framing headers to the
    browser.
