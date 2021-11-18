# prepare-vm
A script for the configuration of an Ubuntu-based VM with minimal effort.

It should work out of the box with:
```
install [-u <USERNAME>] [--skip-gerrit]
```
USERNAME is guest by default.

If you do not need to clone from gerrit, then use ```--skip-gerrit```.
Otherwise you need a file gerrit.json like this:

```
{
  "name": "gerrit",
  "user-email": "<my email>",
  "user-name": "<my name>",
  "host": "<gerrit hostname>",
  "base-url": "ssh://<my login name>@<gerrit hostname>:<gerrit port>",
  "description": "projects hosted on gerrit",
  "families": [
    {
      "name": "project family name",
      "description": "",
      "projects": [
        {
          "name": "project name",
          "url": "gerrit project url"
        }
      ]
    }
  ]
}
```

The script will create a directory per project family under gerrit and
then will clone the project under that directory.

You will be asked to copy manually the SSH keys in your gerrit.
