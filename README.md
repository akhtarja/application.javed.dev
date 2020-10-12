# application.javed.dev

This repository contains the codebase for https://application.javed.dev. This site is simply an embedded TypeForm.

The serverless deployment process creates an S3 bucket called `appluication.javed.dev` to hold the assets. This can be changed by editing the value of `APP_BUCKET_NAME` in `app/serverless.yml`.

The build process simply copies the index.html from to the `/build` folder, and the deploy process copies the file to the S3 bucket called `application.javed.dev`. This requires a profile in your local shared AWS credential files.

## Development
To do dev work on the site, open the local `index.html` in your browser. To get hot reloading and some other nice featuers, use a VS Code extension such as [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer).

## Deployment
This process requires an AWS credential profile called `application-javed-dev` in your local AWS shared credential files.

Go to the project's root and do the following:
```
npm install
serverless deploy --profile application-javed-dev
npm run build
npm run deploy
```
