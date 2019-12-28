# Setup Remote content plugin
<!-- position: 1 -->

Bludit supports using remotely-hosted content. In this example, we will walk you through the setup of a GitHub repository and the plugin configuration with a Bludit default setup to get started.
For example, the [Bludit Blog](https://blog.bludit.com) works with this plugin, and the content of the site is on Github in this repository: [https://github.com/bludit/blog](https://github.com/bludit/blog). When I want to create a new page, I create the page and upload it to Github (push).

## Prerequisites

You need a [GitHub](https://www.github.com) account. It's free, and allows unlimited public *and* private repositories, so quickly get one.

This tutorial will assume that you are using [GitHub Desktop](https://desktop.github.com/) to create and manage your repository, and that your Bludit blog was installed on _https://blog.mydomain.com_ for url references below.

## Prepare your git repository

Create a directory in your system named _bludit-tutorial_. Then open GitHub Desktop, click on the upper left part to create a new repository (click on _Add_ and choose _Create new repository_).

Name your repository _remote-content-example_, give it a quick description and find your _bludit-tutorial_ folder for the _Local Path_ and hit the _Create Repository_ button. This will create a new subfolder _remote-content-example_ in your _bludit-tutorial_ folder.

In order for Bludit to parse your content correctly, you will need to set up some folders in this structure:

* _root_
    * pages
        * _page A folder_
            * index.txt
        * _page B folder_
            * index.txt
        * ...

In practice, you can open your created repository in Explorer (Windows) or Finder (MacOS) and create the following folders and files:

* remote-content-example _(already exists by now)_
    * pages
        * first-page
            * index.txt
        * second-page
            * index.txt

Here's some demo content to put in your files:
_blog-content/pages/first-page/index.txt_
```markdown
# First Page
<!-- date: 2018-10-10 20:00:00 -->
Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages.

This is the first page for Remote Content Example.
```

_blog-content/pages/second-page/index.txt_
```markdown
# Second Page
<!-- date: 2018-10-10 21:00:00 -->
Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages.

This is the second page for Remote Content Example.
```

GitHub-Desktop will show you all the changes you made. Enter _This is the initial commit_ as a commit message and hit _Commit to master_. Now publish your repository (which means it will be uploaded to your GitHub Account) and open the repository in a browser by going to _https://github.com/yourusername/remote-content-example_.

## Enable and Configure the Bludit remote content plugin

### Prepare the Bludit Plugin
Log into the admin backend of your Bludit installation, and go to the plugins section. Scroll down until you see the 'remote content' plugin. Click on 'activate' and then on 'configuration'. Copy the full URL that is shown below the _webhook_ input element (Ex. _https://blog.mydomain.com/9as7dfsd98f) into your clipboard (_Ctrl + c_ or _cmd + c_).

### Configure your GitHub repository
In a new browser tab (or window) go to your GitHub repository and open the _Settings_. Go to the _Webhooks_ section and create a new webhook. Insert the copied webhook url into _Payload URL_ field and switch _Content Type_ to _application/json_. Now click on _Add webhook_.

### Add your repository zip file location to Bludit
Switch back to your repository main page, and copy the URL of the zip package from the _clone or download_ section. Add the full URL to the Bludit Plugin configuration field named _Source_. Save the plugin configuration.

## Make your first push
Now go back to your local repository, and create a new page:

* remote-content-example
    * pages
        * third-page
            * index.txt

_blog-content/pages/third-page/index.txt_
```markdown
# Third Page
<!-- date: 2018-10-10 22:00:00 -->
Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages.

This is the third page for Remote Content Example.
```

Commit your changes as before, and push them to the remote repository. After this, GitHub will let Bludit know about the changes thanks to the webhook. Bludit will grab the zip file from the configured path, and parse the pages from your repository.

Well done!

## Structure of index.txt
The pages that are imported via remote content need to follow this structure in order to parse correctly:

* First line: title of the page with a leading #
* Then all metadata you want to provide such as creation date, publish status etc. wrapped by html content notation (`<!--` and `-->`)
* Your content

```markdown
# This is the page title
<!-- date: 2018-10-10 22:00:00 -->
<!-- put some metadata here -->
Here comes your content
```

## Example repository and video tutorial
We also prepared a video tutorial, and an example repository for you too.
- [Repository](https://github.com/bludit/remote-content-example)

<div class="video-embed">
	<iframe width="640" height="360" src="https://www.youtube.com/embed/Kzh_Wl2ZovQ?rel=0&amp;showinfo=0" frameborder="0" gesture="media" allowfullscreen></iframe>
</div>
