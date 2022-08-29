# Golden Platform starer

This repository is a helper repository to start working on the Golden Platform from [PlatformOS](https://www.platformos.com).



## Prerequisites
We are using a collection of tools that one should understand to work with the Golden Platform, at least the basics of.
1. A basic understanding of [command line](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/Understanding_client-side_tools/Command_line)
1. A basic understanding of [GIT](https://git-scm.com/videos)
2. [GIT Submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules) for using various modules developed for the Golden Platform
3. The very basics of [npm](https://nodejs.dev/en/learn/an-introduction-to-the-npm-package-manager) for developement tools
4. Understanding of [PlatformOS](https://www.platformos.com/documentation)
5. The [Liquid Markup](https://documentation.platformos.com/api-reference/liquid/introduction) for building templates and provide dynamic configuration



## How to start developing using the Golden Platform

### Get the codebase

**If you are using [HTTPS](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)** to authenticate with GitHub:
1. Clone the repository with
   ```
   git clone https://github.com/Platform-OS/pos-golden-starter.git
   ```
2. Open `.gitmodules` from the root directory of cloned repository and edit all of the URLs from default SHH to HTTPS line in the example:
   `git@github.com:Platform-OS/pos-module-core.git` to `https://github.com/Platform-OS/pos-module-core.git`
3. Save the file
4. Run the following command from the root of the repository folder to install all of the submodules:
   ```
   git submodule update --init --recursive
   ```

**If you are using [SSH](https://docs.github.com/en/authentication/connecting-to-github-with-ssh)** to authenticate with GitHub:
1. Clone the repository using following command (this will install the default modules as well):
   ```
   git clone --recurse-submodules git@github.com:Platform-OS/pos-golden-starter.git
   ```

### Install the PlatformOS Command Line Interface
The [pos-cli](https://documentation.platformos.com/developer-guide/pos-cli/pos-cli) is a command line interface that helps you deploy configuration files and assets to your platformOS site.

Assuming you already have [npm](https://nodejs.dev/en/learn/an-introduction-to-the-npm-package-manager) installed on your system just run:
```
npm install -g @platformos/pos-cli
```


### Create your PlatformOS instance
Assuming you already have [an account](https://partners.platformos.com/accounts/sign_up) in the PlatformOS partners portal and are [logged in](https://partners.platformos.com/accounts/sign_in):
1. Go to https://partners.platformos.com/instances/new
2. Follow [instructions](https://documentation.platformos.com/get-started/marketplace-template/marketplace-template#step-2-create-instance) on screen
3. From the root repository directory add the instance to pos-cli config using
   ```
   pos-cli env add dev --email <YOUR_EMAIL> --url <YOUR_INSTANCE_URL>
   ```

This will add the instance with an `dev` alias as the developement tools assume this will be the name of your default developement instance. You can change it to whatever name you want but some of the npm commands are assuming that `dev` is the default.



### Deploy the code
1. In the command line go to the root of the cloned repository
2. Run
   ```
   pos-cli deploy dev
   ```
3. Open your instance URL in the browser to verify if everything went successfully. You should see a waving hand emoji (👋).



### Start developing
[TBD]

You can try how [hook system](https://github.com/Platform-OS/pos-module-core) and [theme manager](https://github.com/Platform-OS/pos-module-theme-manager) works, you can create your own [module](https://github.com/Platform-OS/pos-module-template) or [theme](https://github.com/Platform-OS/pos-theme-module-template) to test it.


You always need to add `git submodule update` when core, theme manager or admin modules are outdated.
