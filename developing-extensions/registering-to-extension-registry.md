# Registering to Extension Registry

When you complete your extension development, you can register your extension to **Extension Registry** so that users can install your extension easily via **Extension Manager**.

## First Registration

If you created your own extension and want to release the first version, then please follow the below steps.

### Create `package.json`

Create a `package.json` file. `name` field is a unique identifier for the extension. We recommend to combine your Github id and repository name. For example, if your Github id is `john` and the repository name is `sql-generator`, then `john.sql-generator` could be good for `name` field. `version` field has to be set carefully. Recommend to follow [Semantic Versioning](http://semver.org/).

> Note that `name` field should be lowercase alpha-numeric name without spaces. It may include "." or "\_" or "-" characters.

Following is an example for Java extension.

```javascript
{
    "name": "staruml.java",
    "title": "Java",
    "description": "Java code generation and reverse engineering.",
    "homepage": "https://github.com/staruml/Java",
    "issues": "https://github.com/staruml/Java/issues",
    "keywords": ["java"],
    "version": "0.9.0",
    "author": {
        "name": "Minkyu Lee",
        "email": "niklaus.lee@gmail.com",
        "url": "https://github.com/niklauslee"
    },
    "license": "MIT",
    "engines": {
        "staruml": ">=3.0.0"
    }
}
```

### Write README.md

Please write information and user manual of your extension in `README.md` file.

### Upload to Github

Upload your extension source codes to a Github repository. Only Github is supported, so others \(e.g. Bitbuckets, etc.\) are not supported. When user install an extension, then **Extension Manager** downloads extension directly from the Github repository.

### Create a release

Finally, you have to create a release in the Github repository as described in [https://help.github.com/articles/creating-releases/](https://help.github.com/articles/creating-releases/). This is very important. Without this, extensions cannot be downloaded from **Extension Manager**. The `tag version` and `release title` should be matched with the `version` field in the `package.json` file.

### Send email

After creating a release, just send email to us \(`support@staruml.io`\) with your extension repository URL. Then, we will register your extension to **Extension Registry** within one or two business days.

## Upgrading to New Version

If you want to release a new version of your extension already registered in **Extension Registry**. Please check the followings.

### Check `version` in `package.json`

Set new version number in `version` field in `package.json`.

### Create a new release

You have to create a release for every version. Check again that the `tag version` and `release title` are matched with the `version` field in the `package.json` file.

### Send email.

After creating a new release, just let us know that new version is released by sending email to us \(`support@staruml.io`\). We will upgrade your extension to the new version within one or two business days.

