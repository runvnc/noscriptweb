# NoScriptWeb

For some context, read  [Adblocking, How about Nah?](https://www.eff.org/deeplinks/2019/07/adblocking-how-about-nah)

# Work in Progress (just started)

*Note: What this actually does so far* Right now (after two days of actual coding) it is sort of like a janky RST viewer that only knows about headings and paragraphs.  Not useable for anything.

I have also done some research into `dat`, `ipfs`, `gnunet` and `libp2p`.  Planning on using `libp2p` because of issues (such as poor performance for this task or installation problems) with the other options.

# Everything below here is just an idea -- not actually coded yet

NoScriptWeb is a new type of lightweight, high-performance document/wasm browser that is *100% JavaScript free*. Pages are encoded in an encrypted, size-limited subset of restructuredtext distributed in a content-oriented (rather than server-centric) fashion. They load almost instantly from network peers.

This software is written in the [Nim](https://nim-lang.org) programming language.

## Ad-free

It is impossible for ads from the traditional web to display in NoScriptWeb, or for companies to track you -- because no content or links from the traditional web can be displayed by NoScriptWeb browsers.

This web browser is a relatively simple system, rather than an entire operating system-in-a-box like Chrome or Firefox. It is supported by decentralized protocols.
 
## RST (restructured text) subset
 
NoScriptWeb RST supports the following features: headings (with `#`), escape with backtick, bold, italics, bullets, and links (only to other NoScriptWeb pages, e.g. nsw://reports.frontline/aug2019austin).
 
## Attachments
 
All non-markdown content (except for one small image) is loaded *only* upon demand by the user.
 
Media and applications can be attached to pages, but have restrictions.  No more than 10KB of images will be loaded by default.

Other than that small image, media must be launched explicitly from the Media tab.  Zero bytes will be loaded, processed, or transmitted without prompting by the user.

### Media attachments

Pages may attach images or videos.  Their descriptions appear on the Media Tab.  Users must switch tabs and click the individual media item before any loading or processing is done.  Images and media may not be loaded from traditional web sources outside of NoScriptWeb  protocols.

### Application attachments

Applications may be attached to pages.  They appear on the Applications tab and are not downloaded or executed unless explicitly launched by the user.

Attached applications are written in web assembly with some basic I/O abilities which include:

* A [simple UI API](https://github.com/simple2d/simple2d)

* A communications API that connects applications with NoScriptWeb's p2p backbone

* Carefully controlled payment prompts that integrate popular cryptocurrencies.  Available cryptocurrencies currently include: Bitcoin, Ethereum, and Bitcoin Cash.

## P2P Search

All markdown content is automatically added to a full-text search system.  This search capability is powered by the peers in the network.
