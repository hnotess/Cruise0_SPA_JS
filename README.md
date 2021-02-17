# Demo Application for Cruise0

This is a proof-of-concept demo app for Cruise0, built off of the [NodeJS/Express SPA Quickstart App](https://auth0.com/docs/quickstart/spa/vanillajs).

## Running the Application

The app can be run locally, by cloning the repository to your machine and then following the steps below. The Auth0 credentials in `auth_config.json` are included for convenience.

### Installation

After cloning the repository, run:

```bash
$ npm install
```

This will install all of the necessary packages in order for the sample to run.

### Running the Application

This version of the application uses an [Express](https://expressjs.com) server that can serve the site from a single page. To start the app from the terminal, run:

```bash
$ npm run dev
```

Then navigate to localhost:3000 in your browser to use and interact with the sample app.

## Requirements

This app was designed to meet the following requirements (and meets them partially):

### Show how Auth0 can support the Cruise0 app modernization on ReactJS (you are free to build the PoC single page application in your preferred language for demonstration purposes).

✅ The Quickstart templates for Auth0 demonstrate many proof-of-concept approaches for different tech stacks. I built this one off the Vanilla JS template, but there are options for [React](https://auth0.com/docs/quickstart/spa/react) as well.

### Show how a new customer can sign up, and how an existing customer can sign in with email/password, and Google.        

✅ This app makes use of Auth0's [Social Identity Providers](https://auth0.com/docs/connections/social/) feature, using Auth0's default credentials for Google apps, set up via the [Auth0 Dashboard](https://auth0.com/docs/get-started/dashboard/set-up-social-connections
)

### Ensure that customers who login with username/password and Google, with the same email address, will be treated as the same user. Also known as Account Linking.

✅ This app implements Account Linking via the [Account Linking Extension](https://auth0.com/docs/extensions/account-link-extension).
)

### The application should display an error if the customer’s email address is not verified. 
⚠️ This requirement was partially implemented. The customer's email address verification status is fetched from [the user object in the Auth0 Management API](https://auth0.com/docs/api/management/v2/#!/Users/get_users) and displayed in the dropdown after the user is logged in. However it just displays "true" or "false", not a proper user-friendly error message. To fully implement this requirement, you could use conditional logic to display the error message based on whether the user's email is verified. 

### Use Auth0 features to customize the profile page so both the photo and country flag are displayed without prompting users to input directly. If the photo and country of the customer are known, make sure this information is passed back to the application and shown after the user authenticates.       

⚠️ This requirement was partially implemented. The profile page displays the photo as well as the other user data stored, including location and country data, in JSON format. The location data was added using [Auth0 Rules](https://auth0.com/docs/rules/create-rules). However the profile page doesn't display the country flag. To fully implement this requirement, you could grab a library of country flags such as [FlagKit](https://github.com/madebybowtie/FlagKit) and match them to the country codes stored in the user data.  

## Author

[Auth0](auth0.com), [@hnotess](https://github.com/hnotess)

## License

This project is licensed under the MIT license. See the [LICENSE](LICENSE.txt) file for more info.
