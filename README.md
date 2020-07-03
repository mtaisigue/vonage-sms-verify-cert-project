# Implementing Certification Project for SMS & Verify API certification

This repo contains the code for the [certification project](https://vonage-workshop.nexmodev.com/verify/certification/certification-project/) on using the Nexmo Verify ans SMS API. It is written in Node.js using the Express framework.

## Get the code
Follow these steps to get your own version of this up and running:

```bash
git clone https://github.com/mtaisigue/vonage-sms-verify-cert-project.git
cd vonage-sms-verify-cert-project && npm install
```

## Configuring the application
Once installed, copy the `env-example` file to `.env` in the application's root directory. Enter your API key, secret and virtual number from the [Nexmo Developer Dashboard](https://dashboard.nexmo.com) and also a name for your application which will appear on the home page and also in the `from` field of any SMS sent via the Verify API.

```
NEXMO_API_KEY=<your_nexmo_api_key>
NEXMO_API_SECRET=<your_nexmo_api_secret>
NEXMO_BRAND_NAME=<your_brand_name>
VIRTUAL_NUMBER=<your_nexmo_virtual_number>
```
## Running the application
Start a proxy session with ngrok using ngrok http 3000, then go to your Vonage Dashboard and update the inbound SMS webhook for your virtual number to point to /webhooks/inbound-sms
You should then be able to run the app with `npm start`.

Then on two different browser windows (if using the same browser one of these should be a private window) login as a "Driver" first on one browser and as a "Rider" in the other one. Make sure you use 1XXXXXXXXXX format for USA when entering your phone number e.g. (14152324093)

After login, as a Rider select a Driver from the list (dropdown) and click on "Contact your driver". both should receive an SMS and can start texting each other using that sms thread.
