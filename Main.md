# Notes on AI realization
*This is Keng's personal notes on essential ideas to realize AI, from the perspective of Computer Science, Quantum Physics, Mathematics and Philosophy.*`

`Dec 2014`

As preliminary, we assumed a flexible, vague idea of Artificial Intelligence; and do not yet attempt to define it rigorously, until the main idea has taken a sufficiently mature form.


## Loose Definition
Artificial Intelligence is for now loosely defined as man-made entity which can mimic the functionality of a human brain, i.e. manifests `intelligence` and passes the Turing test, effectively deceiving humans. Shortly, to create an AI is to simulate a human mind. Note that we use computers and AI interchangeably, as once an AI is realized on a computer, we can update the definition of computers correspondingly.

Whereas `intelligence` is defined as the ability to obtain, process and utilize information, then carry out strategies to achieve certain aims.



## Feasibility Assumptions
From the standpoint of physics, the human brain is an assemblage of highly ordered matter which can be reproduced if given a complete blueprint. The human brain shall be seen as a superset of the definition of computers that is more universal than the Universal Turing Machine. In principle, if one can sufficiently replicate the neuro-structure of the human brain, together with necessary input/output (perception/action) interface, then one can simulate a fully-functional human mind, i.e. intelligence.

It is intuitive that since the human brain, as all matters in the universe, obey the same physics, the application of these laws guarantees the feasibility of reproducing an intelligent, conscious entity. It is then up to us to reverse-engineer the human brain and its perceptual/actual extensions to obtain a blueprint for AI.


## Origin of this Work
The idea first started in Summer 2014 at the Perimeter Institute for Theoretical Physics, when the author discussed the definition of intelligence with his colleagues. The discussion was influenced by their background in quantum physics and quantum information/computation. 

Later, when the author was delving in computer science and doing theoretical math, the idea came into mind: "Can a computer do proofs like a mathematician?" 

#### The Difference between a Computer and a Human Mind

The gap between the capability of a computer and a functional human mind is too wide – computers are built of a simplistic model of logic and math, and are restricted by deterministic, macroscopic(classical) physical laws; whereas the human mind is capable of randomness and creativity, and is believe to operate on the level of quantum physics.

As of this time, computers are defined through automata and the Universal Turing machine. On the surface, computers do calculations algorithmically; while human minds seem to operate with randomness and free will.

Consider the next generalization of computers by this: when is a human's thinking most like a computer, i.e. most strictly logical. Doing mathematical proofs immediately came to mind – it is a combination of human creativity and strict logic. This seems an easier leap than to have a computer start doing art like a human.

Therefore, think of how humans do math proofs, and try to classify the types of proofs/theories can and cannot be done by computers. Gödel's theorem immediately comes up.


## Gödel's Incompleteness Theorem and the Limit of Computers
This was one of the first crucial ideas we encountered in a series of "disappointing" discoveries on artificial intelligence. Closely related to the present model of computers, Gödel's Theorem of mathematical logic states that a theory cannot be both consistent and complete. In its common application to replicating the human mind, computers are consistent and therefore incomplete; whereas humans are inconsistent and thus incomplete. This underscores a fundamental difference between the nature of computers and humans. Thus, the next generalization/update of the definition of a computer shall resolve this incompatiblity: i.e. make computers inconsistent and complete. This gives us the first two criteria for a generalization of a computer:

```
1. Update to accommodate quantum randomness.
2. Update to be complete and inconsistent.
```





### v 0.3

A responsive HTML email template that will render consistenly across all email clients.

This template is built upon the results from experiments done in September 2014, documented here [HTML Email Hacks](http://docs.google.com/document/d/1mG0oVZU3_wZCs2y-gLgBuU6pHlxfRsLgL5VujgAqwaQ/edit#heading=h.iq6ygz2ryd38). Moreover, to maximize its full (speed) potential, use the build tool [html-email-generator](https://github.com/maxlapides/html-email-generator).

## Features

* Simplicity via modularity: the best that is achievable
* Easy and quick to use straight out of the box
* 99%-perfect rendering on all email clients.
* Sass-based styling control – DRY and systematic
* Responsive layout
* Bulletproof layout elements: buttons, columns, iconlist etc.

Moreover, unlike many good templates out there that tackle each problem bit by bit, pasting some `<!--[if gte mso 9]>...` code here and there, there isn't even a single use of conditional code inside this template. You do not have to know all the hacks and reset styles; we got that covered. 

You can code your HTML email in Zen with this template.

## Scopes

The HTML email build from this template has been [tested with Litmus](https://litmus.com/tests/18270344/versions/1/screenshots), and will be rendered consistently on these clients:

1. Desktop Clients
  * Apple Mail 6
  * Lotus Notes 8 - 8.5
  * Outlook 2000 - 2013
  * ThunderBird
  * Mailbox app

2. Mobile Clients
  * Native email apps on Android 2.3 - 4.2
  * Native email aps on all iOS devices
  * Gmail app on Android and iOS devices
  * Yahoo Mail app (No mobile-view for now)
  * Mailbox app (No mobile-view for now)

3. Web-based Clients (on Google Chrome, Safari, Firefox, IE.)
  * AOL
  * Gmail
  * Yahoo

## Usage I: straight out of the box

The HTML email template consists of three main files: `index.html`, `style.css`, `style.scss` with Sass partials. One can use the template straight out of the box, or choose to use it with the build tool [html-email-generator](https://github.com/maxlapides/html-email-generator) to its full (speed) potential.

We shall explain the template in the order the parts are listed.


#### 1. `index.html`

##### The `<head>`


First, the `<link>` **CSS stylesheet** import statement allows previewing as you code. When done, copy and paste the compiled CSS into the `<style>`. Then, inline the entire `index.html` using [CSS Inliner](http://inliner.cm/). Bam, you can now send this email.


The **Gmail Promotions Tab** is a new feature for the Gmail web app. It displays a nice profile of the sender. Replace the fields `name`, `url`, `url/googlePlus`, and `image` as needed. More info [here](https://litmus.com/blog/gmail-does-it-again-the-new-visual-promotions-tab).



##### The `<body>`

It is clean, and manages only the **content** and the **position-layout**. Taking the mess out of here – that's the beauty of the template. More specifically, no CSS styles are inlined within the body. The perfect (consistently rendered) content layout is achieved using merely tables. Typically, no more than 4 layers of table nesting is required.



  1. **Classes**: The template does the minimal by declaring the classes in `<table>`, `<td>`:


    * **sizes** – `width` and `height`, if not already explicitly declared.

    * **labeling** – *row, col, container, button* etc. , for targeting the CSS styles using specificity.
  
    * **states** – hide on mobile, re-center, stack columns etc. , represent the states to apply to the object when email is rendered on different screen sizes.


    Complete detail is documented inside the Sass files. The classes are declared in order:

    ```
    <table width="280" class="full col-1 flow" ...>
    ```


    Firstly, the outermost table is `void`, which is the 100% container that houses and centers the 600px content.

    On the second layer, all contents are segregated into modular `rows`. The spacing between the rows is done by `hutter` – a vertical analogue of `gutter` (spacing between columns).

    Each content row can have any layout. Included samples are rows with *one, two and three columns, icon list, menu bars, and buttons*.



  2. **Attributes of `<table>`**: Note that every `<table>` tag must have its `cellpadding`, `cellspacing`, `border` set to zero, (except for cellpadding occasionally; see next).



  3. **Padding**: This has been the main isssue that plagues most email coders. A typical solution is to replicate padding using empty table cells, which overly complicates the code and rigidify the layout.

    Guess what, we solved the problem: **Use `cellpadding`**. This attribute is so elementary that *everything* must support it. Yes, it works in all the clients that we've tested above, even in the old Outlook. 

    Here is a sample usage of the classes and cellpadding:

    ```
    <table class="full row-t1" cellpadding="20" cellspacing="0" border="0">
    ```
    This table is the "test-1 row", has a full 600px-width, and will take up 100% of the screen size when shrunk. It has a padding of 20px. Sitting immediately inside it:

    ```
    <tr><td class="full-padded container">
    ```
    ```
    <table class="full-padded" cellpadding="0" cellspacing="0" border="0">
    ```
    is the container within the padded parent, which has width of 600 - 2(20) = 560px.




#### 2. `style.css`

This is simply the output rendered from the Sass files. Copy and paste its content into the head `<style>` tag before inlining the html, as described above. The template works straight out of a box like a website template with any compiler, such as CodeKit.



#### 3. `style.scss` and the Sass partials

This is the main magic that makes our `index.html` simple. It manages all the layout control and styling. All the CSS styles are done with Sass, which is even cleaner due to its powerful modularity.

Included in it are the styling techniques and template elements, such as `buttons`, that are guaranteed to always work.


* `style`: the main Sass file; imports `typography` and `layout-controls`. Note that it also imports the reset styles `reset-head` and `reset-inline` when the build tool is not used.

* `_typography`: controls the typography and color.

* `_layout-controls`: responsive layout control and styling.

* `_layout-invariants`: class-declaration and setup for layout-controls.

* `_auxiliary`: other layout elements such as buttons, borders, rounded-corners.

* `_fluid`: The media queries and mixins for responsive design.

* `_variables`: widths and heights of table elements, padding and etc.

* `_colors`: color code.

* `reset-head` and `reset-inline`: The reset styles (hacks) that fix many rendering problems caused by different email clients. These are inlined into the `<head>` and element tags in the `index.html`.


Detailed explanation is documented in the files.




## Usage II: with the html-email-generator

The usage is pretty much the same as described above, but the build tool will tremendously improve your workflow by automating many pesky tasks. Visit [html-email-generator](https://github.com/maxlapides/html-email-generator) for details.

The file structure of the template has been setup to work directly with html-email-generator. Simply set up the build tool and run `gulp`, then recover your built file from the tool's `build` folder when done.

Keep in mind that, when using the build tool:

* Use `html.handlebars` in place of the `index.html`.

* `reset-head` and `reset-inline` are implemented automatically by the build tool rather than imported by `style.scss`.

* Live-preview-and-editing from the tool.

* CSS is compiled from the Sass and inlined automatically into the built `index.html` file everytime you save. This is the ultimate time-saver.




## Changelog

### v 0.3 (Oct 2014)
* A major refactoring of the code, with many simplifications.
* Discovered ways to exploit `cellpadding` - a total godsend.
* A complete rewrite of the `index.html` layout template. It is now cleaner, simpler to use, more powerful that before – works on all the tested clients perfectly.
* Added the Gmail Promotions Tab snippet into `<head>`.
* Updated `reset-head` and `reset-inline` with new results.
* Rewrote and reorganized most of the Sass files - now DRYer.
* Now the rendered CSS styles are shorter, and has no duplicates.
* Significant update of the `fluid` styles.
* Created a button mixin – 100% bulletproof, configurable and simple.
* Added a mixin – transform a link into button on mobile.
* Added a `recenter` mixin – stacks and centers adjacent columns on mobile.
* Added more layout styles.
* Researched more on Yahoo and Mailbox apps, updated on Google docs. Confirmed it impossible to turn convert a web-version email into a mobile-version.
* Completed documentation and user-guide.


### v 0.2 (Sept 2014)
* Fixed some layout issues and improved the aesthetics of `index.html`
* Added documentation of hacks in `hacks.html`
* More layout templates: bicolumns, tricolumns, menu bars, etc.
* `_auxiliary` has more elements: borders, rounded, buttons using mixins
* Simpler, more extensive layout and styling control with better documentatio.

## Roadmap

### v 0.3
* Update and move the HTML email Hacks document to GitHub.
* Fix the 1% flaw.
* Observe beefree.io
* Even more template layouts.
* Use Handlebars' templating features.
* Tackles the Gmail, Yahoo, Mailbox mobile apps by using a reverse approach: Start out with mobile design, then turn it into a web-version.

The last obviously requires compromise – customer has to agree to mobile-first, which is not hard to convince. Over 65% of emails were opened on a smartphone or table, [report here](http://blog.movableink.com/new-research-shows-mobile-dominates-desktops-with-65-of-total-email-opens-in-q4-2013/).

 The mobile-version will be rendered on the web-clients that do not support media queries; web-version will be rendered whenever prossible, on Apple desktop Mail, Outlook webmail, AOL webmail. [Data here](http://freshinbox.com/blog/email-client-media-query-and-embedded-styles-support-2014/).


