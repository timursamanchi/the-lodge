# @the-lodge

Jenkins Github-webhook test

## Jenkins Github-webhook configuration

Configurations needs to be done on the jenkins server pipeline job side and on github repo side.
NOTE: The project must run at least one successful build before connecting to GitHub. This allows Jenkins to read the configuration from the repo

### 1) Jenkins pipeline job configuration
- Select GitHub Project and paste in the repo URL (optional)  
- Under Build Triggers, select the checkbox next to GitHub hook trigger for GITScm polling  
- Under Pipeline, select Pipeline script from SCM  
- Under SCM, select Git  
- Under Repository URL, paste in the repo URL  
- Under Branch Specifier (blank for 'any'), change master to main (important)  
- Save → Build Now  

### 2) Github repo configuration
- Copy the URL of your Jenkins server (right click on the jenkins logo)  
- Select Settings → Webhooks → Add webhook  
- Under Payload URL, paste in the URL for your Jenkins server (copied from jenkins logo)  
- Immediately after the Jenkins server URL, add /github-webhook/ (important)  
- Under Content type, select application/json  
- Add webhook

NOTE: GitHub will ping the Jenkins server and indicate a successful connection with a green checkmark next to the webhook name. If your webhook does not indicate that it connected successfully, select Edit and confirm your settings again. If needed, delete the webhook and start over.











