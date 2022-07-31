# prepare-vm
A script for the configuration of an Ubuntu-based VM with little or no effort.

It should work out of the box with:
```
install [-u <USERNAME>] [--brew]
```
USERNAME is assumed to be guest by default.

If you want to install gerrit repos, there is another script:
```
gerrit
```

To be launched typically from your $HOME.

It expects in the same place a gerrit.json file like this:

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

The script will create a directory per project family under /gerrit and
then will clone the project under that directory.

You will be asked to copy manually the SSH keys in your gerrit.

|  version | Ubuntu                                              | Mint                     |
| ---------| ----------------------------------------------------| -------------------------|
| 2.0      | 22.04 :heavy_check_mark:                            |                          |
| 1.2      | 20.04.3 :heavy_check_mark: 22.04 :heavy_check_mark: | 20.03 :heavy_check_mark: |
| 1.1      | 20.04.3 :heavy_check_mark:                          | 20.03 :heavy_check_mark: |
| 1.0      | 20.04.3 :heavy_check_mark:                          | :x: |

