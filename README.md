# Google IOX Extended Web App
Standard Web App for IOx's Events.
Show some ❤️ and star the repo to support the project

![image](https://github.com/vrijraj/iox24-webapp/assets/10599101/f8bbafd3-7cd0-4401-a4ba-ed788b3df5bd)

## Getting Started
1. Fork the repo
1. Setup Environment
    - Install [Node.js (v20 or above)](https://nodejs.org/en/download/)
1. Install project dependencies: `npm install` 
1. Compiles and hot-reloads for development use `npm run dev`
1. Update JSON files from `/assets/data` and `/public/` directory
1. Upload all the images related to Speakers, Team and Sponsors in `/public/speakers/` | `/public/team/` with their respective directory
1. For the production: `npm run generate` and then one dir will be created dist

Look at the [Nuxt 3 documentation](https://nuxt.com/docs/getting-started/introduction) to learn more.

## Deployment on Firebase
1. Install required tools for performing Firebase deployment
    - Install Firebase CLI: `npm i -g firebase-tools`
1. Login into Firebase CLI using the following command -  `firebase login`
1. Now type `firebase login` command in your Terminal/CMD/Powershell
1. Update the `Firebase Project ID` in `.firebasesrc` file. This value should match the project ID in your Project Settings of the Firebase project you created in the previous section.
1. Go to the Firebase Console Dashboard and Click on Hosting in the left navigation.
1. Click on Get Started
1. Click through all steps till you’re taken to the Hosting page in the console.
1. You’ll be provided with a ready domain with your project ID. It should look like - `<project-id>.web.app or <project-id>.firebaseapp.com`
1. Copy the sub-domain name of the URL provided. In this case, it will be the project ID. However, to be precise, you have to copy the part before .web.aap or .firebaseapp.com. This is your Site ID
1. Update `Firebase.json` file, set the site key to Site ID
    ```js
        {
            "hosting": {
                "site":"Your_Firebase_Hosting_id",
                "public": ".output/public",
                "rewrites": [ {
                    "source": "**",
                    "destination": "/index.html"
                } ],
                "ignore": [
                    "firebase.json",
                    "**/.*",
                    "**/node_modules/**"
                ]
            }
        }
    ```
1. In your terminal at the root directory of the project,  build and deploy using the following command     
    - `firebase deploy`

## Technology Stack
1. [Vrijraj Singh](https://vrijraj.xyz/)
2. [Shivam Singh](https://shivam.live/)
3. [Sandali Singh](https://sandali.xyz/)

## Technology Stack

* [VueJS](https://vuejs.org/)
* [Nuxt](https://nuxt.com/))
* [Firebase](https://firebase.google.com/)


## Contributing

Awesome! Contributions of all kinds are greatly appreciated. To help smoothen the process we have a few non-exhaustive guidelines to follow which should get you going in no time.

## LICENSE
Check out the developer [LICENSE](https://github.com/vrijraj/devfest-website-2023/blob/main/LICENSE)

## Facing Any Problem or need any Help?
Write us in [issues](https://github.com/vrijraj/devfest-website-2023/issues) section. Our team will try solve your issue within 10-12 hours.<be>
