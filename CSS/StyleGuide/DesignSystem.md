# Design System (Thinking)

* Design System - The whole design language of the system. Voice and Tones, Typography, Brand Identity, Copy Writing, Color Palettes, Icons, Grid System, Code, UI Patterns, etc. 
* [Style Guides](http://bradfrost.com/blog/post/style-guides/) - Guidelines to styles. Cornerstones of a good design system.
* Pattern Library - Documented UI library with code examples.
* Content Patterns - the content strategist's job to define content patterns
* Display Patterns - the designer's job

> Get control over your design with a system

Maintain a visual language, UI elements, components and page types to realize substantial efficiencies and consistency. The need for a cohesive design language is high.

Living documentation based on executable examples.

* [Atomic Design](http://atomicdesign.bradfrost.com/chapter-1/)
* [Responsive deliverables - Dave Rupert](http://daverupert.com/2013/04/responsive-deliverables/)
* [Why and How to Test your Pattern Library](http://tinnedfruit.com/2016/09/12/why-and-how-to-test-your-pattern-library.html)
* [Test your Design System, not your website](http://tinnedfruit.com/2015/08/01/test-your-design-system-not-your-website.html)
* [31 Ways to Spend Less Time on Manual Cross-Browser Testing](http://tinnedfruit.com/2016/08/15/31-ways-to-spend-less-time-on-manual-cross-browser-testing.html)
* [Style Guide Resources](http://styleguides.io/)
* [A Design System isn't a Project. It's a Product, Service Products.](https://medium.com/eightshapes-llc/a-design-system-isn-t-a-project-it-s-a-product-serving-products-74dcfffef935#.wme8nk6gp)
* [Designing Modular UI Systems Via Style Guide-Driven Development](https://www.smashingmagazine.com/2016/06/designing-modular-ui-systems-via-style-guide-driven-development/)
* [Tokens in Design Systems](https://medium.com/eightshapes-llc/tokens-in-design-systems-25dd82d58421#.m9zvc5sj6)
* [The Salesforce Team Model for Scaling a Design System](https://medium.com/salesforce-ux/the-salesforce-team-model-for-scaling-a-design-system-d89c2a2d404b#.5uq1gbyrb)
* [Content Display Patterns - Content patterns are different from Display patterns](http://danielmall.com/articles/content-display-patterns/)

> Your design needs to adapt and change to fit the content on offer and the changing nature of the web. Whether it's a modified navigation bar to accommodate new sections, a new type of article page or a complete design refresh, the key to success is continuous improvement.

---

> A developer using a CSS library will not apply their own `padding: 16px` rule, but will apply grid classes to elements to conform to the specification.

---

> Our gaze remains transfixed on the final product, and we rarely if ever glance at the underlying patterns that comprise our final UIs.
> 
> Of course, there is another way to approach your LEGO and digital projects. Rather than diving headfirst into constructing the final work, you can take the time to take stock of the available pieces and organize them in such a way that they become more useful.
> 
> No doubt organizing takes time, planning, and effort. It doesn’t come for free. The fact that this configuring isn’t visibly represented in the final product may tempt us to say it serves as a distraction to the real work that needs to be done. Why bother?

## Pattern Library

* [FutureLearn](https://www.futurelearn.com/pattern-library)
* [Polymer Library - Learn from it!](https://www.polymer-project.org/1.0/)

## Broader Strokes - Style Tiles, Element Collages

To establish aesthetic direction, mood and atmosphere.

## Company Design Language

http://styleguides.io/examples.html

* [Yelp](https://www.yelp.com/styleguide)
* [Apple Develop](https://developer.apple.com/develop/)
* [Android Develop and Design](https://developer.android.com/design)
* [IBM Design Language](http://www.ibm.com/design/language/)
* [Lonely Planet](https://rizzo.lonelyplanet.com/styleguide)
* [FT's Origami](http://origami.ft.com/)
* [FT Next](https://github.com/Financial-Times/next)
* [Buzz Feed](http://solid.buzzfeed.com/buttons.html)
* [Airbnb - The way we build](http://airbnb.design/the-way-we-build/)
* [Nordnet](https://www.nordnet.se/brand/ui/)
* [Intuit](http://harmony.intuit.com/)
* [USA Gov](https://standards.usa.gov)
* [MailChimp](http://ux.mailchimp.com/patterns)

## Context-Agnostic and Structural Thinking

* [Architecting a Pattern Library](http://us5.campaign-archive1.com/?u=7e093c5cf4&id=ead8a72012&e=ecb25a3f93)

> These blocks can be manufactured in parallel because their underlying structure (typography, spacing, button styles) are already in place! 

See how Structural Engineer evaluate a land for foundation.

The more agnostic pattern names are, the more versatile and reusable they become.

Instead of "homepage carousel", simple called it "carousel". Instead of "product card", simply called it "card". Don't be distracted by the content patterns that live inside them.

> For instance, if working on an e-commerce site, you may be tempted to call a block containing a product image and title a "product card". But naming things in this manner immediately limits what type of content can live inside it. By naming the pattern simply "card", you can put all sorts of content patterns inside it: products, promotions, store locations, and so on.

Naming things is really hard. But by conducting an Interface Inventory, you can remove patterns from the context of the page where they normally reside, meaning your team can create names that aren't distracted by their context/content.

Focus on the pattern's structure rather than the content that lives inside it.

Make it agnostic by naming patterns according to their structure rather than their context or content.

You may have a **content model** you identified as Event, with these pieces of information: Title, Date and Location. You probably will mark them up as BEM:

```html
<div class="event">
  <h1 class="event__title">Star Wars</h1>
  <p class="event__date">Dec 20, 2015</div>
  <p class="event__location">Ritz East</div>
</div>
```

But nothing says that Event's content model can't be for Article also. What we need is to extract a Display Pattern out of it. 1 single Display Pattern that can result in many Content Patterns.


## Maintenance

A Design System needs ongoing maintenance, support, and tender loving care for it to truly thrive.

> A style guide is an artifact of design process. A design system is a living, funded product with a roadmap & backlog, serving an ecosystem. - Nathan Curtis

To prevent the system from being eroded by a series of one-off changes, we need to make changes at the system-level rather than at application-level.

Do not anyhow add new patterns to library. Similarly, do not be afraid to create brand new patterns. If every whim results in a brand new pattern, the design system will become a bloated and unwieldy Wild West. It's worth asking if this is a one-off situation or something that can be leveraged in other applications.

> It often falls to the developer to see through the pixels of a comped element to find the actual design pattern. This is why development is design.

---

> I'm finding that I have the most success when my Display patterns don't describe the content within and when my Content patterns don't suggest anything about their presentation.

## Videos

* [Can't You Make It More Like Bootstrap? – Alice Barlett from FT](https://www.youtube.com/watch?v=y4ggoN2xtAY)
* [Thingness - Mark Boulton](https://vimeo.com/163510673)