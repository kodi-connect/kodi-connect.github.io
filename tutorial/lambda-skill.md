Here's the long part. Please follow these steps _very carefully_.

---

## Region Select
**This step is VERY IMPORTANT.**

At the top right of the screen, there is a button next to your username, but before the "Support" button. It may have the name of a region. You must click it and select the correct Lambda Function Region according to your Alexa language.

Amazon provides a list of [regions and languages](https://developer.amazon.com/docs/smarthome/develop-smart-home-skills-in-multiple-languages.html#deploy). Here is a copy:

Skill language                                           | Endpoint Region | Lambda Function Region
---------------------------------------------------------|-----------------|-----------------------
English (US), English (CA)                               | North America   | US East (N. Virginia)
English (UK), French (FR), German, Italian, Spanish (ES) | Europe, India   | EU (Ireland)
English (IN)                                             | Europe, India   | EU (Ireland)
Japanese, English (AU)                                   | Far East        | US West (Oregon)

For example, I am located in Slovakia, but my Amazon Echo devices are set to "English (US)". For this step, I would choose "US East (N. Virginia)".

---

## Setting up AWS Lambda - Part 1
1. Click on the Services button at the top left. In the list, look for the "Compute" section, and click on "[Lambda](https://console.aws.amazon.com/lambda/home)".
1. Click on the orange "[Create Function](https://console.aws.amazon.com/lambda/home?#/create)" button.
1. Make sure the "Author from scratch" tile is selected.
1. Set the following options:
    * Name - "kodi"
    * Runtime - `Node.js 12.x`
1. Under "Permissions" section expand "Choose or create an execution role"
1. Ensure that "Create a new role with basic Lambda permissions" is selected
1. Click the "Create Function" button.

Leave this window/tab open, as we will need to return back to it.<br/>
But copy the function ARN that is in the upper right corner, which should look something like this: 

`arn:aws:lambda:<region_you_picked>:<long_number>:function:kodi`

## Setting up Alexa Skill
1. Open [Kodi Connect](https://kodiconnect.kislan.sk) page
1. Log in if you're not already
1. On the Devices page, click the "Alexa skill", which will redirect you to the Amazon website to log in (you need to use Amazon account that you have on your Echo devices).
1. After signing in, you will be redirected back to Kodi Connect page, with a single text input and a button.
1. Here enter the Lambda function ARN, that you've or you can copy from the AWS page, where you've created it (`arn:aws:lambda:<region_you_picked>:<long_number>:function:kodi`), and press "Create skill" button
1. Give it a few seconds, and it will create whole skill for you, and present you with the skill ID (`amzn1.ask.skill.2ba4b05b-3bd2-46b1-bbb5-15153ff41a48`). Copy it, as you'll need it in next step.


## Setting up AWS Lambda - Part 2
1. Go back to the page from "Part 1", or if you've closed it, [AWS Lambda](https://console.aws.amazon.com/lambda/home), and go to function "kodi"
1. In the "Designer" section, click on the "+ Add trigger" button, then pick "Alexa Smart Home" from the dropdown.
1. In the "Application ID" box, paste the "Skill ID", that you've copied in the previous section (e.g. `amzn1.ask.skill.2ba4b05b-3bd2-46b1-bbb5-15153ff41a48`).
1. Make sure "Enable Trigger" is checked. Click "Add" at the bottom right.
1. Download the zip file with the Lambda function code from [here](https://kodi-connect.s3.eu-central-1.amazonaws.com/kodi-alexa-video/kodi-alexa-video-package-1.0.zip)
1. Then in the same section, click on the name of your function (should be "kodi").
1. In the "Function code" section below, look for "Code entry type". Click on this menu, and select "Upload a .zip file".
1. Click the "Upload" button, and select the zip file we downloaded earlier (e.g. `kodi-alexa-video-package-1.0.zip`).
1. Click "Save" at the top right of the page, and wait for it to load.
