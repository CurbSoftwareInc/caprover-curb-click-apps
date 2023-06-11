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
In the 'One-Click Apps' database, paste the copied YAML from the application you want from this repository. Click 'Next' and follow the remaining instructions. This will include choices about whether to enable SSL, HTTPS, web sockets, and other settings.

![Paste YML Code](https://github.com/CurbSoftwareInc/caprover-curb-click-apps/raw/main/instruction-images/instruction-paste-yml-code.png)

For the ToolJet app, it is not a production setup, and you can also help to increase security by adding basic authentication. For some apps, you may want to disable user registration after your admin user has been added in the environment variables.

Additional environment variables are included in the markdown readme files in each of the application folders on this repo. Make sure to refer to these for application-specific settings and configurations.

**Note**: These instructions are only a guideline. Each application may have specific requirements or additional steps to function correctly. Always refer to the specific readme file in each application folder for detailed instructions.


Remember, these instructions are only a guideline. Each application may have specific requirements or additional steps to function correctly. Always refer to the specific readme file in each application folder for detailed instructions.

## Contribute
This project exists thanks to all the people who contribute. Feel free to make your own modifications and open pull requests. Any contributions you make are greatly appreciated.

## Contact

Your Name - legend@curbsoftware.com

Website - [CurbSoftware Inc - Risk Management, Business Process Automations, and WordPress Development](https://curbsoftware.com)


Project Link: [https://github.com/CurbSofwareInc/caprover-curb-click-apps](https://github.com/CurbSofwareInc/caprover-curb-click-apps)
  
## Contributors

Thank you to all the contributors who participate in this project now and going forware.

<table>
  <tr>
    <td align="center"><a href="https://github.com/CurbSofware"><img src="https://github.com/CurbSoftware.png" width="100px;" alt=""/><br /><sub><b>Robert Alexander</b></sub></a><br /></td>
    <td align="center"><a href="https://github.com/DeviousJack"><img src="https://github.com/DeviousJack.png" width="100px;" alt=""/><br /><sub><b>The Most Devious of Jacks</b></sub></a><br /></td>
  </tr>
</table>

## License

GNU General Public License v2.0
