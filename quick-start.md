---
layout: default
title: Quick Start to Tiny Cloud
description_short: Setup TinyMCE in less than 5 minutes (on your desktop).
description: Get a local instance of TinyMCE up and running in less than 5 minutes.
keywords: tinymce script textarea
---

TinyMCE is a powerful and an incredibly flexible text editor that helps you in creating great content regardless of your level of expertise.

This is the place to begin if you are new to TinyMCE and want to get a local editor instance up and running in less than 5 minutes (via our TinyMCE Cloud). We will guide you about features such as advanced installation options, working with plugins, learning about content filtering, and spell checking.

If you prefer to download TinyMCE and install it locally the [Advanced Install]({{  site.baseurl }}/general-configuration-guide/advanced-install/#packagemanagerinstalloptions) page in the Self-hosted Get Started guide has instructions.

Now, back to the TinyMCE Cloud. In the next 3 steps – and in less than 5 minutes – you'll have a basic, local editor instance up and running.

## Step 1: Include the TinyMCE script

Include this line of code in the `<head>` of your HTML page:

```html
<script src='{{ site.cdnurl }}'></script>
```

> Tip: We give you a complete html snippet in Step 2.


## Step 2: Initialize TinyMCE as part of a web form

With the script included, initialize TinyMCE on any element (or elements) in your web page.

Since TinyMCE lets you identify replaceable elements via a CSS selector, all you need to do is pass an object that contains a `selector` to `tinymce.init()`.

In this example, let's replace `<textarea id='mytextarea'>` with a TinyMCE editor instance by passing the selector `'#mytextarea'` to `tinymce.init()`.

```html
<!DOCTYPE html>
<html>
<head>
  <script src='{{ site.cdnurl }}'></script>
  <script>
  tinymce.init({
    selector: '#mytextarea'
  });
  </script>
</head>

<body>
<h1>TinyMCE Quick Start Guide</h1>
  <form method="post">
    <textarea id="mytextarea">Hello, World!</textarea>
  </form>
</body>
</html>
```

> Note: If you're testing this locally, you will need to prepend `https://` to urls in the `script` tag. For example, `<script src='https:{{ site.cdnurl }}'></script>`.

## Step 3: Saving content with a form POST

When the `<form>` is submitted the TinyMCE editor mimics the behavior of a normal HTML `<textarea>` during the `post`. In your form handler, you can process the content submitted as if it had come from a regular `<textarea>`.

And that's all there is to it!

You may use TinyMCE Cloud without an API key. However, to use our premium plugins or avoid the in-editor developer warning, you will need to sign up for an API key and update the script tag used to load the editor code into your application. Please visit the [Cloud Deployment Guide]({{  site.baseurl }}/cloud-deployment-guide/) to learn more about the plugins and other features of TinyMCE.


