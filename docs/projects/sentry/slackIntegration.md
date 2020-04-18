## How to fix issue of client ID when integrating Slack to Sentry locally

 - Create a Slack Workspace  on [https://api.slack.com/apps/new_app_token](https://api.slack.com/apps/new_app_token)
 - Once the workspace has been created, copy your workspace credentials such as:
   1. Client_ID
   2. Client_Secret
   3. Verification Token
  - Also In the slack app page go to the "Oauth & permissions" page and add your domain to the redirect urls. e.g. [https://sentry.mycompany.com](https://slack-redir.net/link?url=https%3A%2F%2Fsentry.mycompany.com&v=3)
 - After you've done that and gotten the following credentials, copy and paste the credentials in the Sentry onpremise  *config.yml* file, you can get the folder [here](https://github.com/getsentry/onpremise)
 **Note:** You are to paste it in this form:


       slack.client-id: "xxxxxxxxxxx.xxxxxxxxxxx"
       slack.client-secret: "xxxxxxxxxxxxxxxxxxxxxx"
       slack.verification-token: "xxxxxxxxxxxxxxxxxxxxx"
- After that build a new docker image with your changes.

```
$ docker build -t sentry-local:latest -f docker/Dockerfile
```
- Once image is properly built, run sentry locally using [sentry/onpremise](https://github.com/getsentry/onpremise) repo.
**Note:** In the `onpremise` repo, remove this [line](https://github.com/getsentry/onpremise/blob/master/install.sh#L109) that pulls sentry from dockerhub from your local repo. Once that line has been removed, build sentry-onprem docker image using the code below:
```
$cd onpremise/
$SENTRY_IMAGE=sentry-local:latest  ./install.sh
```
- You're all done start docker-compose to launch your local sentry.
```
$docker-compose up -d
```
- You're all set, If you try to integrate Slack locally it should work now
