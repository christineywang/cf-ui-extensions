## Contentful UI Extensions for Everyone :grin: :tada:

:warning: IN PROGRESS!

[Contentful](https://www.contentful.com/) allows users to install extensions to the web app interface so that the current user interface can be "extended" to look or do something different than what is presently available. If you aren't a developer-type, they may look intimidating to install at first but rest assured--after this workshop, you will be a UI extensions pro. :+1:

#### Jump to:
- [What is a UI extension and why do they matter?](#what-is-a-ui-extension-and-why-do-they-matter?)
- [Who can make a UI extension?](#who-can-make-a-ui-extension?)
- [Where can I find example extensions?](#where-can-i-find-example-extensions?)
- [Okay, enough of the small talk--let's install an extension!](#okay-enough-of-the-small-talk-lets-install-an-extension!)

<hr>

### What is a UI extension and why do they matter?

You probably already use extensions everyday in your web browser. They allow you to customize your browsing experience and access other services outside what is native to your browser (such a  :rainbow:  picker--I have [this](https://goo.gl/xdYHW) one installed!).

Contentful UI extensions are slightly different because users can't just go to a "store," browse for extensions, and click a button to install the extension. Contentful require the extension code (plain HTML files) to be uploaded to Contentful in order for the user to be able to access the custom functionality. The extension code is then included in all of the code that makes up the web app (which is built on top of our Management API).

Giving users the ability to customize the web app is important because Contentful doesn't always know (or can accommodate) custom use cases. Also, sometimes extensions can help fill a gap in the interface for a feature that would be very helpful for our users (and may even be on our product roadmap) but is not built yet. An example would be our slug generator, which can now be added as an _Appearance_ option for our short-text field. But did you know it was a feature that was once only available as a [UI extension](https://github.com/contentful/extensions/tree/master/samples/slug)?


### Who can make a UI extension?
Any user with some knowledge of code can write their own extension by using our [UI Extensions SDK](https://github.com/contentful/ui-extensions-sdk). :punch:

### Where can I find example extensions?
We have a [Github repository](https://github.com/contentful/extensions) with sample UI extensions and most recently, users are sharing their own creations [here](https://www.contentfulcommunity.com/c/ecosystem/show-us-your-extension). :beers:

### Okay, enough of the small talk--let's install an extension!

For the workshop, we will be installing a very simple extension: [Rating Dropdown](https://github.com/contentful/extensions/tree/master/samples/rating-dropdown)

This extension gives users another appearance option for the number field type.

#### What you will need:
- A Contentful space ID
- Your personal access token
- The files for the extension in a folder on your desktop

#### Create a content type
To start, let's go into our Contentful space and create a sample content type that will use the the Number field. You can add a _Text_ field (I'm going to name mine _Title_) and a _Number_ field.

When you click on _Create and configure_ > _Appearance_, you will see that we have four different builtin options for how this field can currently look right now: _Number editor_, _Dropdown_, _Radio_, and _Rating_. You can use the default appearance.

Save your content type.

#### Installing the extension to your space
In order to install the extension, we will be using the folder on our desktop that contains the two files we need for the extension:
`app.html`
`extension.json`

Now, the next step is where it could look tricky (but it's really not!).

Open the command line on your computer. The command line is basically a way for you to "command" your computer what to do without having to use the user interface that comes with your computer.

:white_check_mark:	_You may have heard about our CLI tools. Anytime you hear that, think "Command Line Interface."_

We will be using a command called `npm` to perform the next few steps. This is something that needs to be installed on your computer first. The easiest way to do it is to install [Node.js](https://docs.npmjs.com/getting-started/installing-node).

npm install -g contentful-cli
What is `npm`? Here is our UI Extension CLI on the npm website:
https://www.npmjs.com/package/contentful-extension-cli

We will be using the `npm` command to install the extension. But this will only work if you have this command installed.

If you are following along, the easiest way to do it is to install Node.js:
https://docs.npmjs.com/getting-started/installing-node

`npm install -g contentful-extension-cli`


Now, from the command line, we are going to move into the folder where the two files for the extension is stored.

If you are following along, the command is:
`cd <yourFolder>`


From here, we will perform this command:
`cd <path-to-your-folder>`
This means, whatever action we take now will be



FAQs:
- Extensions are installed on a space-basis
- What fields can be changed using the UI extension? (https://www.contentful.com/developers/docs/concepts/editor-interfaces/)
