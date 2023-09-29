Thank you for your interest in contributing to the Unetus Docs.

## Site overview and markdown styling

The Unetus documentation site is built using [Jekyll](https://jekyllrb.com/), a static site generator and [Bootstrap 5](https://getbootstrap.com/docs/5.0/getting-started/introduction/). When updating content, navigate to:

* the `inso-cli` directory for Inso CLI documentation pages
* the `insomnia` directory for Unetus (client) documentation pages

### Use Markdown instead of HTML

Stick to Markdown as much as possible in Markdown files. Use the following classes to style elements:

Element | Markdown class
------- | --------------
table | `{:.table .table-striped}`
note callout | `{:.alert .alert-primary}`

### Accessibility

The Unetus documentation site aims to follow [AAA WCAG accessibility standards](https://www.w3.org/WAI/WCAG2AAA-Conformance).

Since we use [Bootstrap 5](https://getbootstrap.com/docs/5.0/getting-started/introduction/) and it tends to be accessibility-friendly, use their HTML where you need accessible elements and you cannot easily create them with Markdown.

### Add a new page

Add a new page if you are adding documentation for a new topic. Don't add a new page for FAQ-type content. Take time to see where the content fits in.

* Add the file to either the `inso-cli` or `insomnia` folder. 
* Name the file descriptively and use full words where possible. 
* Add the page title and local url to `_data` > **main-nav.yaml** under the corresponding section.

### Keep it simple

* Don't add unnecessary and excessive packages.
* **Use screenshots very sparingly**. And if you add a screenshot, ensure it has descriptive alt text and a short description underneath. See [Introduction to Unetus](/insomnia/get-started) for an example.  
* Use the Oxford Comma to prevent any misinterpretation.
* Use Vanilla JS where needed. No need to add jQuery.
* For icons, use [Google Icons](https://fonts.google.com/icons). This means we don't have to download an entire library to use just a few icons.

### Capitalization

Capitalize the following words, as they refer to entities in our client:

* Project
* Collection
* Document
* Snapshot
