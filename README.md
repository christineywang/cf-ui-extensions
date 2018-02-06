## Contentful UI Extensions for Everyone :grin: :tada:


[Contentful](https://www.contentful.com/) allows users to install extensions to the web app interface so that the current user interface can be "extended" to look or do something different than what is presently available. If you aren't a developer-type, they may look intimidating to install at first but rest assured&mdash;after this workshop, you will be a UI extensions pro. :+1:

#### Jump to:
- [What is a UI extension and why do they matter?](#what-is-a-ui-extension-and-why-do-they-matter)
- [Who can make a UI extension?](#who-can-make-a-ui-extension)
- [Where can I find example extensions?](#where-can-i-find-example-extensions)
- [Okay, enough of the small talk&mdash;let's install an extension!](#okay-enough-of-the-small-talk&mdash;lets-install-an-extension)
- [FAQs](#faqs)

<br>
<hr>
<br>

## What is a UI extension and why do they matter?

You probably already use extensions everyday in your web browser. They allow you to customize your browsing experience and access other services outside what is native to your browser (such a  :rainbow:  picker&mdash;I have [this](https://goo.gl/xdYHW) one installed!).

Contentful UI extensions are slightly different because users can't just go to a "store," browse for extensions, and click a button to install the extension. Contentful requires the extension code (plain HTML files) to be uploaded to Contentful in order for the user to be able to access the custom functionality. The extension code is then included in all of the code that makes up the web app (which is built on top of our Management API).

Giving users the ability to customize the web app is important because Contentful doesn't always know (or can accommodate) custom use cases. Also, sometimes extensions can help fill a gap in the interface for a feature that would be very helpful for our users (and may even be on our product roadmap) but is not built yet. An example would be our slug generator, which can now be added as an _Appearance_ option for our short-text field. But did you know it was once a feature that was only available as a [UI extension](https://github.com/contentful/extensions/tree/master/samples/slug)?

<br>

## Who can make a UI extension?
Any user with some knowledge of code can write their own extension by using our [UI Extensions SDK](https://github.com/contentful/ui-extensions-sdk). :punch:

<br>

## Where can I find example extensions?
We have a [Github repository](https://github.com/contentful/extensions) with sample UI extensions and most recently, users are sharing their own creations [here](https://www.contentfulcommunity.com/c/ecosystem/show-us-your-extension). :beers:

<br>

## Okay, enough of the small talk&mdash;let's install an extension!

For the workshop, we will be installing a popular extension: [Rich-text editor](https://github.com/contentful/extensions/tree/master/samples/alloy-editor)

This extension gives users another appearance option for the long-text field type.

<br>

### What you will need
- A Contentful space ID
- Your personal access token
- The files for the extension in a folder on your desktop

<br>

### Create a content type
To start, let's go into our Contentful space and create a sample content type that will use the the _Text_ field (if you don't have one already). You can add a short-text  _Text_ field (I'm going to name mine _Title_) and a long-text _Text_ field.

When you click on _Create and configure_ > _Appearance_, you will see that we have five different built-in options for how this field can currently look right now: _Single line_, _Multiple line_, _Markdown_, _Dropdown_, and _Radio_. You can use the default appearance.

Save your content type.

<br>

### Preparing to install the extension

In order to install the extension, we will be using the folder on our desktop that contains the two files we need for the extension:

`Makefile`

`extension.json`

`index.html`

`package.json`

<br>

Now, the next step is where it could look tricky (but it's really not!).

- Open the command line on your computer. For Mac users, you can find it from the Spotlight Search (`cmd` + `space-bar`) and typing in _Terminal_.

> The command line is basically a way for you to "command" your computer what to do without having to use the user interface that comes with your computer.

<br>

:white_check_mark:	_You may have heard about our CLI tools. Anytime you hear that, think "Command Line Interface."_

<br>

We will be using a command called `npm` to perform the next few steps. This is something that needs to be installed on your computer first in order for you to be able to access the command. The easiest way to do it is to install [Node.js](https://docs.npmjs.com/getting-started/installing-node).

- Once you have npm, install our CLI tool from the terminal.

- This is the command:
`npm install -g contentful-extension-cli`

<br>

:warning:  _For new extensions, use `npm install -g contentful-cli` since the extensions CLI is getting deprecated._


<br>

### Installing the extension to your space

- Open the `Makefile` file from your text editor of choice.

- Add in your access token and space ID to the top two lines:
`export CONTENTFUL_MANAGEMENT_ACCESS_TOKEN=<your token here>`
`export SPACE=<id of space where you want to install this extension>`

- Save and close the file.

<br>

Now, from the command line, we are going to move into the folder where the files for the extension are stored. Any action we make in the command line moving forward will be using the contents in this folder.

- The command is:
`cd <yourFolder>`

- Once you are in the extension folder, run this command to make sure you have all the dependencies of the extension on your computer:
`npm install`

> Dependencies are other packages in npm that this project uses. In our case, this project contains the `contentful-extension-cli` dependency.

- Next, run this command:
`make create`

- And this:
`make serve`

- This will upload and serve the extension from Contentful.

<br>

### Time to test out the extension!
- Click into the content type we previously created (with the long-text field).
- Next to the long-text field, click on _Settings_ > _Appearance_.

> :boom: :boom: :boom:

- To test out your new editor, change the _Appearance_ of your long-text field to _Rich Text Editor_.

- Click on _Save_ and create a new entry!

<br>

:white_check_mark: _To see the extensions you have installed in your space, go to _Space settings_ > _Extensions_._

<br>


## FAQs
- Extensions are installed on a space-basis
- What fields can be changed using the UI extension? (https://www.contentful.com/developers/docs/concepts/editor-interfaces/)
