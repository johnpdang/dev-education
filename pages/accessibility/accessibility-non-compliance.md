# Accessibility Non-Compliance

{% embed url="https://www.telerik.com/blogs/so-youre-being-sued-for-accessibility-non-compliance" %}

Compliance with web accessibility requirements is good for many reasons—not least of which is potential legal considerations. If you're wondering how to begin with accessibility, here are some tips to get you started.

It’s a day like any other when you open your email or pick up the phone to a real day-ruiner from the legal department: Your organization is being sued because your site or web application doesn’t comply with accessibility guidelines, most commonly [WCAG Level AA standards](https://www.w3.org/WAI/standards-guidelines/wcag/). The only way to protect yourself and your company from [legal action](https://www.telerik.com/blogs/accessibility-and-the-law)? Get to work on making your site or app compliant. _Now._

### Accessibility Is No Longer Something You Can Ignore <a id="accessibility-is-no-longer-something-you-can-ignore"></a>

If this hasn’t happened to you yet, it’s only a matter of time. Accessibility compliance is no longer restricted to public agencies and financial institutions. Law firms are working down a very long, industry-specific list. You’re on it somewhere.

This isn’t just a legal headache, of course. Improving the accessibility of our sites and apps is a worthy and excellent goal. After all, _everyone_ deserves a good user experience. But under the stress and deadline of legal repercussions, the undertaking can seem completely overwhelming.

### Pro Tips for Accessibility Beginners <a id="pro-tips-for-accessibility-beginners"></a>

Don’t worry. We’ll get you started. If you absorb these pro tips, you’ll have a much better idea of how to make your site or app accessible for all.

#### 1. Don’t Rely on the Lawyers’ Scans <a id="don&#x2019;t-rely-on-the-lawyers&#x2019;-scans."></a>

The lawyer sending you compliance nastygrams knows just about as much about accessibility as you do. \(Fun fact: Dollars to donuts, their website isn’t compliant either.\) Overzealous lawyers will be quick to point out items that aren’t issues, and they may miss things that actually do hurt accessibility.

> _**Pro Tip**_
>
> Get your own scanner and [run your own scan](https://www.telerik.com/blogs/solving-the-accessibility-puzzle). You don’t have to spend a fortune. At truematter, we use [Powermapper Accessibility Checker and Validator](https://www.powermapper.com/). It does a good job for a reasonable price.

#### 2. Prepare for a _Lot_ of Gray Area <a id="prepare-for-a-lot-of-gray-area."></a>

Getting a scanner and running a scan is the easy part. The trick is interpreting your scan. Don’t expect a simple checklist where you can mark each item pass or fail. Accessibility guidelines are often open-ended and sometimes confusing. You’ll have to make decisions about the best way to resolve issues. The more extensive and complex your site or app, the more of these tough decisions you’ll have to make.

For example, let’s say you have a PDF printout that contains the same content that can be found on your site. The on-screen content is compliant, but you still fail a guideline because the PDF is not accessible. What do you do with that PDF? Make it compliant? Hide it from screen readers? Omit it? Change your content strategy so you never use a PDF again? These are tough questions. You need expert advice to be sure you’re satisfying accessibility standards without hurting overall usability.

> _**Pro Tip**_
>
> Find an accessibility expert to help you interpret findings and guide you through the tough issues. You _can_ cultivate in-house accessibility expertise, but that will take quite a while. If you’re looking at a lawsuit, hire an expert now and build internal skills later.

#### 3. Don’t Sacrifice Usability <a id="don&#x2019;t-sacrifice-usability"></a>

Some accessibility guidelines can lead the inexperienced to make decisions that fly in the face of good overall UX. It’s no good to fix your site or app for a certain percentage of people only to hurt the experience for the majority of users. Always focus on what makes the best experience for everyone, not on what merely passes a generic scan.

You may have to significantly change content, functionality, or overall strategy to maintain balance between accessibility compliance and overall user experience.

> _**Pro Tip**_
>
> Involve a UX expert. They will evaluate whether your proposed accessibility solutions will hurt overall user experience and come up with strategies to ensure ease-of-use for everyone.

#### 4. Real People are the Best Judges <a id="real-people-are-the-best-judges"></a>

Software is just a starting point. We don’t judge usability exclusively with bots, and neither should we judge accessibility exclusively with software

> _**Pro Tip**_
>
> Run a scan, then test your digital product with real people. Only a person with limited vision can evaluate user experience for people with limited vision. Test your solutions with real people, and you will learn more than any software product can tell you.

#### 5. Be Aware of Common Problem Areas <a id="be-aware-of-common-problem-areas"></a>

You will encounter many accessibility issues specific to your digital product and your digital product. But you can prepare for certain accessibility problems that affect almost every site or app. In fact, you can get started fixing these issues before you ever run your first scan.

**Alternative Text**

For your digital product to pass an accessibility scan, every image must have alternative, or alt, text.

If an image is purely decorative and doesn’t contribute to information on the screen, your alt text should simply be left blank.

![Screen shot of sun icon in an image editor with the &#x201C;Alt Text&#x201D; field highlighted and blank](https://d585tldpucybw.cloudfront.net/sfimages/default-source/default-album/sued-1.jpg?sfvrsn=ba7b94ba_1)

_Empty Alt Text: This sun icon doesn’t add information the user can’t get another way on the screen. The “Alt Text” field, therefore, is blank._

In code, this would look like:

```text
<img src="/theImage.jpg" alt="" />

```

HTML

This tells screen readers to skip the image as not important. On the other hand, if the image provides information you can’t get through words on the screen, you’ll need to write descriptive alt text that clearly explains what the image is communicating.

Let’s say your screen is about a new dog park. One image shows people sitting at a table in the park that’s mentioned in the written content. That image would have empty alt text, because it’s not adding new information that low vision users or blind users couldn’t get another way. But let’s say you have another image that shows dogs getting treats at the park’s concession stand. Your written content never mentions that dog treats are for sale at the park. You’ll need to write alt text for the image that says something like “Dogs getting treats for sale at the park concession counter.” People with low vision or blind people won’t be able to get that information any other way. \(Alternatively, you could add that information to your written content and skip the alt text—just another one of those tough decisions we mentioned earlier.\)

Watch out, you can annoy your user with too much or too little information, same as any other online text. It’s crucial to consider context, brevity, and your users’ tasks as you write alt text. Your UX expert can help you with this too.

> _**Pro Tip**_
>
> We could talk about alt text for an entire article. Fortunately, [WebAim already did](https://webaim.org/techniques/alttext/) and it’s super useful. We like [this list of quick tips](https://a11yproject.com/posts/alt-text/) from The A11Y Project too. Bookmark both and reference them often.

**Color Contrast**

WCAG level AA guidelines specify that text must have a contrast ratio of at least 4.5:1 \(or 3:1 for large text\). This also means that link color must stand out distinctly from regular text. It’s very likely that the text on your site or app utterly fails color contrast guidelines. You can check it out right now. Once again, WebAim comes to the rescue with their [Contrast Color Checker](https://webaim.org/resources/contrastchecker/).

> _**Pro Tip**_
>
> Be prepared to fudge on your brand colors. This might make your marketing team angry. Believe us, no one will know that you had to use a blue two shades off from your brand standard for accessibility compliance. But the accessibility scan and users with limited vision or color blindness will know if you don’t do it.

**Link Text**

This guideline actually warms our content team’s heart. Your button and link text must say specifically where a given link goes. Chuck “Read More” and “Click Here” right out the window. When link text is vague, it’s hard for someone using a screen reader to know where exactly they’re going. \(Heck, it’s hard for everyone else too.

> _**Pro Tip**_
>
> All links should be concise and descriptive. Tell users precisely where links go and what they do. This doesn’t give you license to create nine-word buttons. If you’re doing that, you have entirely separate content strategy problems.

Don’t Do This: A page full of vague, repeated action links is bad enough for sighted users, but for people using a screen reader it’s downright confusing.

**PDF Accessibility**

Surprise! Any PDFs on your site or app must be accessible too. Forewarned is forearmed: Making PDFs accessible is not easy. Set time aside to deal with this issue – you’ll be glad you did.

So how do you make a PDF accessible? There’s a lot to it \(and your accessibility expert will help you\) but here are some things you should know right away:

You need Adobe Acrobat Pro. It will be your best friend. The accessibility tools the software provides will allow you to make any PDF accessible and test for accessibility. Adobe offers strong resources for both. In fact, if you have Acrobat now, you can check your PDFs with their [Accessibility Checker](https://www.adobe.com/accessibility/products/acrobat/using-acrobat-pro-accessibility-checker.html)

Start at the source. Making a PDF accessible after it’s been created is much harder than making it accessible from the beginning. The latest version of Adobe InDesign and Microsoft Word have accessibility features to help you as you create your document.

Be cautious when using the “Make Accessible” Action Wizard in Acrobat. It will do most if not all of the work for you, but you still need to manually review things like color contrast, reading order, and tags for accuracy.

> _**Pro Tip**_
>
> Keep your PDFs simple. The more images, charts, and interactive form elements you have, the more hassle it will be to make your PDF accessible. If that content is truly important, put it on your site. It’s much easier to make a web page accessible than a PDF.

#### 6. Document _Everything_ <a id="document-everything"></a>

Because guidelines and their solutions can often fall into those pesky gray areas, write down all your decisions and reasoning behind them. If you ever need to present your rationale to a lawyer or judge, you’ll be ready to go. And bonus – if you ever need to solve a similar problem again, you can refer to your documentation to figure out what you did and why you did it. You are essentially creating accessibility governance guidelines.

> _**Pro Tip**_
>
> Always cite the specific WCAG guideline when documenting your solution. Not only will this make internal reference far easier, it will also make things convenient for the aggressive lawyers in your life.

#### 7. Stay on Top of it <a id="stay-on-top-of-it."></a>

Making your site or app accessible is just the start. You now have to _keep_ your site or app accessible, and that means vigilance. Scan your product regularly and fix problems as they arise. Incorporate the WCAG accessibility standards into every digital product project you build from here on out.

> _**Pro Tip**_
>
> Schedule a quarterly internal accessibility audit. This is essential to keeping your site or app user-friendly for everyone \(and keeping lawyers at bay\).

#### 8. Train Your Maintenance Team <a id="train-your-maintenance-team"></a>

Nothing will sink your compliance faster than releasing your site or app to content authors and maintenance professionals with no understanding of accessibility guidelines or your commitment to them. You must build internal accessibility awareness and enforce your newfound standards.

> _**Pro Tip**_
>
> Add accessibility to internal maintenance training programs, documentation, and governance guidelines. If you don’t have any of these, now is the time to create them.

### Build With Accessibility In Mind <a id="build-with-accessibility-in-mind"></a>

Accessible digital products are long past due. Moving forward, make sure you never have to go through the cost and frustration of a full accessibility remediation again. Instead, define and design your digital products to comply with accessibility standards from the very beginning.

You’ll need regular input from both accessibility and user experience experts \(either internal or external\). This means your process and documentation must change. But fear not, the added time and budget this requires will more than pay for itself in much-improved digital products and happier customers.

You’ll also know you’re serving _all_ customers excellently – a solid business benefit, and a show of proper good will and respect.

### Learn More about Accessibility

We have created a comprehensive whitepaper on accessibility for developers that covers everything from laws to coding to testing.

**Download the whitepaper:** [Accessibility for Developers](https://www.telerik.com/campaigns/kendo-ui/wp-accessibility)

### Adding Accessibility to Your Apps

One easy way to make sure that you are creating accessible web apps is to start with components from the Kendo UI libraries. Our components are all WCAG complaint and give you great functionality from grids and charts to schedulers and pickers. Get a head start on your app's UI and a head start on accessibility compliance at the same time.

**Learn more about:** [Kendo UI](https://www.telerik.com/kendo-ui)

