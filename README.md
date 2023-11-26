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









