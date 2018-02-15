
## Create a project on Actions on Google  

1. Go on [Actions Console](https://console.actions.google.com/)
1. Click on Add/Import Project
1. Insert project name and Country and click on Create project
1. Keep the page open
1. Go to [Google HomeGraph API](https://console.cloud.google.com/apis/api/homegraph.googleapis.com/overview) and enable it
1. On the left click Credential
1. Create Credential
1. API key
1. Copy the API key shown and insert it in `smart-home-provider/cloud/config-provider.js` instead of `<API_KEY>` in `Config.smartHomeProviderApiKey = "<API_KEY>"`
1. [these
   instructions](https://developers.google.com/actions/smarthome/create-app#request-sync) Launch the following line substituting agentUserId and API_KEY (to understand)

        curl -i -s -k -X POST -H "Content-Type: application/json" -d "{agent_user_id: \"agentUserId\"}" \
            "https://homegraph.googleapis.com/v1/devices:requestSync?key=API_KEY"
1. Install nodejs 9:
        
        curl -sL https://deb.nodesource.com/setup_9.x | sudo -E bash -
        sudo apt-get install -y nodejs
1. Set up the web portal

        cd smart-home-provider/frontend
        sudo npm install -g bower
        bower install
        cd ..
1. Run smart-home-provider-cloud.js, either locally or hosted
    * If running locally

          npm install
          npm start

    * If running in a hosted env,

          node cloud/smart-home-provider-cloud.js smart-home="https://your_domain.com"
1. In a browser, open the ngrok URL shown.
1. Log in with one of the sample user accounts, for instance:

       user: rick
       password: oldman
1. Clicking on the "+" add some controls
1. GO back in the [Console actions project](https://console.actions.google.com/)
1. Reenter the project if exited and click on `Overview`
1. Add action to your app click ADD ACTIONS
1. Go at the beginning of the log of the application in the console and find webhook URL (ending with /smarthome)
1. Under Smart home click BUILD
1. In app information click Edit
1. Give a name and a pronuntiation
1. Fill Details
1. Add images for banner and logo
1. Fill additional info and save
1. Go back to `Overview`
1. Click on `Account linking`
1. ADD
1. Select 'Authorization Code' for Grant Type.
1. Go at the beginning of the log of the application in the console and find Client ID (smartHomeProviderGoogleClientId) and Client secret (smartHomeProvideGoogleClientSecret) to fill the form
1. A little down there is also the Authorization URL (the one ending with /oauth)  and the Token URL (ending in /token)
1. Don't add any scope and fill test instructions and save