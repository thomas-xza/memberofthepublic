### How this stastic site came to exist...

It all started with the humble wishes to put some animations on a static site...

First it was a huge detour into figuring out how to convert .mov files to .avif files, which are apparently the latest hot format for efficiently sized, high quality animations.

The official Github for the foundation behind AVIF turned out to be most useful:<br>
[https://github.com/AOMediaCodec/libavif/wiki/Sequences](https://github.com/AOMediaCodec/libavif/wiki/Sequences)

Then it turned out Cargocollective have revamped their website such that their old hosting service is no longer maintained, and unfortunately rejects anything that is not a `.gif`.

I tried downloading a copy of all the pages of [https://cargocollective.com/memberofthepublic](https://cargocollective.com/memberofthepublic) and simply changing the links (using a script that calls `sed` and `grep`).<br>
...but then the scroll bar was inexplicably broken, and much of the content didn't display properly, and the site's code was far too overcomplicated to actually fix this (somewhere deep in the Javascript is a rudimentary scrollbar).

So then I looked to Llama-4 for a means of AI generating a static site template quickly. I instructed it to use old-fashioned iframes, to prevent having to duplicate the menu across each page, as is common in automated generators.<br>
Llama-4 generated some extraneous code (e.g. a Javascript file which displays/hides an element depending on screen size or something, the whole file needing deleting).<br>
Llama-4 also generated a CSS file with various contradictions that needed demuddling.

I hadn't written CSS for a while but fortunately had retained some rudimentary knowledge; enough to figure out how to position the menu where I wanted:
- as a sidebar when viewing from a large enough monitor, similar to the original site
- underneath the content when viewing from a small sized device (unlike the original Cargocollective site)

And at the point of writing this, it is now just a matter of getting the content to migrate from Github to a long-term, reliable (i.e. well funded, established company) hosting provider, automatically.
I wasn't entirely sure if Cargocollective will really exist forevermore, so prefer to lean on big tech nowadays.<br>
Target is currently Cloudflare Pages and Google Firebase.
