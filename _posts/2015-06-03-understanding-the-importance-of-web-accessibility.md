---
layout: post
title: "Understanding the Importance of Web Accessibility"
excerpt: "Web accessibility all too often is overlooked or simply left out of the process entirely. This is rather unfortunate because it is estimated that roughly one-fifth of our population has a disability of some sort."
tags: [accessibility]
comments: true
---

Web accessibility all too often is overlooked or simply left out of the process entirely. This is rather unfortunate because it is estimated that roughly one-fifth of our population has a disability of some sort.

These disabilities can include:

- Vision, hearing, motor, and cognitive impairments
- [Photoepilepsy](http://www.webmd.com/epilepsy/guide/photosensitive-epilepsy-symptoms-causes-treatment)
- Abilities due to aging

If your website does not meet accessibility standards, roughly 20% of your audience potentially has some barrier to interacting with you. Think of a person relying on a screen reader to provide him or her with feedback on a document download page with a list of 20 items. If the link text or link title descriptions are not descriptive enough, how can this person be sure they are selecting the appropriate link?

## What is Web Accessibility?
Web accessibility provides a means to allow those with disabilities to effectively use the web. Websites or web software programs that neglect to consider this introduce accessibility barriers. These barriers make it difficult or impossible for those with disabilities to use web.

To gain a better understanding of these difficulties, I encourage you watch the video below, courtesy of WebAIM.

<iframe width="420" height="315" src="https://www.youtube.com/embed/yx7hdQqf8lE" frameborder="0" allowfullscreen="allowfullscreen"></iframe>

[Video Transcript](http://webaim.org/intro/media/asd.htm)

## Standards
To date, there is no single solution to capturing and resolving all accessibility barriers. The web is no longer static. It is responsive, displayed on multiple devices, and can have any number of technologies built into it.

The standards we have in place today are [508 Compliance](http://www.access-board.gov/guidelines-and-standards/communications-and-it/about-the-section-508-standards/guide-to-the-section-508-standards) and [Web Accessibility Initiative Guidelines (WCAG)](http://www.w3.org/TR/WCAG20/#a). **508 Compliance** is the law that requires federal agencies and their contractors to adhere to a minimal level of accessibility to electronic and information technology. [The Web Accessibility Initiative (WAI)](http://www.w3.org/WAI/) was formed by the [World Wide Web Consortium (W3C)](http://www.w3.org/) in order to bring accessibility considerations (WCAG) into the technology development.

Both have an extensive list of guidelines and recommendations and can seem rather daunting at first glance. [508 Compliance](http://webaim.org/standards/508/checklist) and [WCAG](http://webaim.org/standards/wcag/WCAG2Checklist.pdf) have checklists as a good starting point, but generally speaking you can begin by tackling the key areas listed below:

- **Label your form elements**
    - <script src="https://gist.github.com/greggnakamura/cd8a2660d550be370a9d.js?file=web-accessibility.html"></script>
    - Associate form ‘for’ labels with their associated form ‘id’ controls. Screen reader can associate the label text when the user select that particular form control.

- **Alternate text for non-text content**
    - Alternate description value is read by screen readers

- **Color contrast**
    - Provide enough contrast between text and its background so it can be seen by those with low vision
- **Descriptive link text**
    - “click here” and “more” read by screen readers provide no context
- **Don’t use color as the only indication of meaning**
    - Barrier to types of color-blindness
- **Add captions to audio content**
    - Videos and live audio should have captions and a transcript available. Audio can simply have a transcript

## Tools
Thankfully, there are a wide range of tools at our disposal that we can use to capture issues with automated and manual checkers. Some of those tool are:

- [Accessibility Developer tools](https://chrome.google.com/webstore/detail/accessibility-developer-t/fpkknkljclfencbdbgkenhalefipecmb?hl=en)
    - Chrome extension. Displays a list of rules which are violated by the page
- [capybara-accessible](https://github.com/Casecommons/capybara-accessible)
    - Run tests, auto generate any failures
- [Contrast Ratio checkers](https://leaverou.github.io/contrast-ratio/)
    - Color combination checker
- [AMP Express](https://amp.ssbbartgroup.com/express)
    - Checks your website against more than 900 individual conformance criteria for accessibility standards like Section 508 and WCAG.
- [AChecker](http://achecker.ca/checker/index.php)
    - Checks a single web page against accessibility standards
- [Tenon.io](http://tenon.io/)
    - Test a site’s accessibility
- [accesslint.com](http://accesslint.com/)
    - Alerts you of common accessibility issues on a page

## Increasing Accessibility
Our job, from Designer, to Developer, to Content Editor, is to eliminate barriers whenever and wherever we can. While it ultimately may not be possible to cater to everyone, we should at least provide some sort of alternate solution.

*“If we can make the effort to care about cross-browser compatibility then we can make the effort to care about cross-person compatibility.”* – [Jonathan Snook](http://snook.ca/archives/accessibility_and_usability/what_does_accessibility_mean/)


