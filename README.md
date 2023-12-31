## Repo for CapRover One Click Apps

### How to create a one-click app (as of v1.8.0):
First, have a look at [this simple example](https://github.com/caprover/one-click-apps/blob/master/public/v4/apps/privatebin.yml). Now, read on for more details:


- Find/create a docker-compose file for the app you're interested in.
- Add `captainVersion: 4` to the very top of the yaml file.
- Add this section to the end of the yaml file:
```yaml
caproverOneClickApp:
    variables:
        - id: '$$cap_myapp_version'
          label: Awesome App Version
          defaultValue: '1.2.3'
          description: Check out their Docker page for the valid tags https://hub.docker.com/r/....../tags
          validRegex: '/.{1,}/'
    instructions:
        start: |-
            A description that will be displayed to the user when they
            are installing one click app!
            It can be multiline and contain more details and probably special
            hardware requirements!
        end: |-
            A summary when the app is deployed!
            It can be multiline.

            It can also include the dynamic parameters such as
            $$cap_appname and $$cap_other_random_char
    displayName: The Awesome App
    isOfficial: true ## Only if all images used here are official or from a trusted source.
    description: A relatively short description, less than 200 characters.
    documentation: This docker-compose is taken from example.com
```

### Variables:
- Variables are prefixed with `$$cap`
- Variables can be anywhere in the content and they will be replaced by what user enters
- There are 3 special variables that are built-in for all oneclick apps: `$$cap_appname`, `$$cap_root_domain`, and `$$cap_gen_random_hex(length)`. For example, if your app needs environment variables with the URL value of the app, you can use `$$cap_appname.$$cap_root_domain` which resolves to something like `myappname.rootdomain.com`. Also If you need a default password, you can use `$$cap_gen_random_hex(10)`
- Each custom variable must have `id`, `label`. They could also have `defaultValue`, `validRegex`, `description`.
- IMPORTANT: by default, fields are not required to be filled. If validRegex is not set, the field can be set as empty and ignored by the user.


### Services:
- Other than `image`, `environment`, `ports`, `volumes`, `depends_on`, and `hostname`, other parameters are currently being ignored by CapRover. If you need a particular parameter, please file an issue, and we'll add it to the respected list.
- Services have a special subsection specific to CapRover called `caproverExtra` which contains service specific parameters that are only available via CapRover and not docker compose. Currently this field can take the following variables:
    - `dockerfileLines` which is a multiline variable, and can be used instead of `image` property in the service. You must delete the `image` property if you want to use this parameter.
    - `containerHttpPort` is useful when the underlying service uses a custom port for HTTP. If not provided, the default will be `"80"`
    - `notExposeAsWebApp` can be set to `"true"` when the underlying service is not an HTTP app. This is useful for databases and other internally used services.
    - `websocketSupport` can be set to `"true"` to automatically enable Websocket Support. Only supported in versions 1.12+

### Icon
- Make sure you add an app icon to the logos directory!


---------


## Test your One Click Apps
After creating your One-Click app yaml file, you need to test it before creating a Pull Request. Here is how you test it:
- Login to your CapRover dashboard
- Go to **apps** and click on **One-Click Apps/Databases**
- Select **>> TEMPLATE <<** at the bottom of the dropdown list
- Copy and paste your YAML into the text area, and click **NEXT**.
- Enter values and make sure it's working as expected.

---------

## Build your own one-click app repository
You may want to build your own private repository. CapRover supports having multiple repositories. You can add new repository URLs to the one click app page. The official one, this one, is available as `https://oneclickapps.caprover.com`.

To create your own repository:
- Fork this repository
- Delete all existing apps (to avoid duplicate apps), and add your own apps.
- Run `npm i`
- Run `npm run validate_apps`
- Run `npm run formatter-write`
- Run `npm run build`
- Now you can host the static content placed in `./dist` directory anywhere you want, the official repo uses [github pages](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site) to publish the content. Make sure to update [CNAME](https://github.com/caprover/one-click-apps/blob/master/public/CNAME) to your own URL if you decide to do so.

### Third party One Click Apps

In order to add a third party repository:
-   Login to your CapRover dashboard
-   Go to **apps** and click on **One-Click Apps/Databases** and scrolldown to the bottom
-   Under **3rd party repositories:** copy  the URL, (for example: `https://Awes0meHub.github.io/caprover-one-click-apps`) and paste it in to the text box
-   Click the **_Connect New Repository_** button

#### 3rd party repositorie
-   Awes0meHub: [Github](https://github.com/Awes0meHub/caprover-one-click-apps) repository: `https://Awes0meHub.github.io/caprover-one-click-apps`
-   Jordan-hall: [Github](https://github.com/Jordan-Hall/caprover-one-click-apps) repository: `https://oneclickapps.libertyware.io`


# Caprover Curb-Click-Apps
## Some (non-official) one-click-apps for CapRover

This is a completely open source repo containing Caprover applications that I have either improved to help make them work or have added new applications. Feel free to make your own modifications.

## CapRover
Easiest app/database deployment platform and webserver package for your NodeJS, Python, PHP, Ruby, Go applications.
No Docker, nginx knowledge required!

- CapRover's Official Repo [https://github.com/caprover/caprover](https://github.com/caprover/caprover)

- CapRover's One-click-apps [https://github.com/caprover/one-click-apps](https://github.com/caprover/one-click-apps)

- CapRover's Website [https://caprover.com/](https://caprover.com/)


## Table of Contents
- [Getting Started](#getting-started)
- [Usage](#usage)
- [Contribute](#contribute)
- [License](#license)

## Getting Started
This section will guide you on how to get the applications running on your CapRover instance.

### Prerequisites
- Make sure you have Caprover installed and running on your system.

### Installation
1. Choose an app that you want to try.  Right now we have:

- [Working one-click version of Kimai](https://www.kimai.org/) With Kimai, the boring process of feeding Excel spreadsheets with your working hours is not only simplified, it also offers dozens of other exciting features that you don't even know you're missing so far!
- [Tooljet](https://www.tooljet.com/) Build complicated internal tools quickly with less engineering efforts. Maximize productivity, reduce costs, and deploy faster with our enterprise-grade open-source low-code platform.
- [Vikunja](https://vikunja.io/) The open-source, self-hostable to-do app. Organize everything, on all platforms.

## Usage
In each application folder, there is a list of environment variables that you can add. Here is how you can use these applications on your Captain server:
Feel free to make your own modifications. Each folder includes a list of environment variables that you can add. Here are the step-by-step instructions on how to use the applications:

### Step 1: Copy the YAML file
Find the YAML file of the application you want to use in this repository and copy its content.

### Step 2: Set up your domain
Make sure that you have a wildcard domain pointed to the IP address of your Caprover server, or you can use the application name of your choice as a subdomain. If you are using Cloudflare, do not activate the proxy on your subdomain until you've activated Let's Encrypt SSL. Once Let's Encrypt is activated, you can enable the proxy on Cloudflare.

### Step 3: Open your Caprover server
Navigate to the applications page on your Caprover server. Click on the 'One-Click Apps' database. Scroll to the bottom of the page and select the file labeled 'template' with the Caprover logo.

![Add One Click App](https://github.com/CurbSoftwareInc/caprover-curb-click-apps/raw/main/instruction-images/instruction-add-one-click-app.png)

### Step 4: Select Template
Select the 'Template' option with the CapRover logo.

![Select Template App](https://github.com/CurbSoftwareInc/caprover-curb-click-apps/raw/main/instruction-images/instruction-select-template-app.png)

### Step 5: Paste the copied YAML
In the 'One-Click Apps' database, paste the copied YAML from the application you want from this repository. Click 'Next' and follow the remaining instructions.

![Paste YML Code](https://github.com/CurbSoftwareInc/caprover-curb-click-apps/raw/main/instruction-images/instruction-paste-yml-code.png)

### Step 6: Visit the app config in your CapRover Dashboard

This will include choices about whether to enable SSL with Let's Encrypt, force HTTPS, enable web sockets, and other settings.


### Other Info:

For the ToolJet app, it is not a production setup because it's usint the tooljet/try image.

You can also help to increase security by adding basic authentication for apps exposed to the interwebs 😜. 

For some apps, you may want to disable user registration after your admin user has been added in the environment variables.

Additional environment variables are included in the markdown readme files in each of the application folders on this repo. Make sure to refer to these for application-specific settings and configurations.

**Note**: Remember, these instructions are only a guideline. Each application may have specific requirements or additional steps to function correctly. Always refer to the specific readme file in each application folder for detailed instructions.


## Contribute
This project exists thanks to all the people who contribute. Feel free to make your own modifications and open pull requests. Any contributions you make are greatly appreciated.

## Contact

Your Name - legend@curbsoftware.com

Website - [CurbSoftware Inc - Risk Management, Business Process Automations, and WordPress Development](https://curbsoftware.com)


Project Link: [https://github.com/CurbSofwareInc/caprover-curb-click-apps](https://github.com/CurbSofwareInc/caprover-curb-click-apps)
  
## Contributors

Thank you to all the contributors who participate in this project now and going forward.

<table>
  <tr>
    <td align="center"><a href="https://github.com/CurbSofware"><img src="https://github.com/CurbSoftware.png" width="100px;" alt=""/><br /><sub><b>Robert Alexander</b></sub></a><br /></td>
    <td align="center"><a href="https://github.com/DeviousJack"><img src="https://github.com/DeviousJack.png" width="100px;" alt=""/><br /><sub><b>The Most Devious of Jacks</b></sub></a><br /></td>
  </tr>
</table>

## License

GNU General Public License v2.0
