missing purchase block, re-ingest PO: http://search-ods.ebf.odsprocessor.walmart.com/search-raw.html find PO_SHIPPED -> purchaseOrderNo, re-ingest PO
missnge shipment no, find shipmentNo in orderLines. order quantity info, if it is missing in shipments block, after Orion to re-publish shipmentNo topic.


Instead, fork this repo so that you get your own repsoitory.
Then clone the repo you just forked.
Add an upstream remote to get the changes we do. Run the following commands:
git remote add upstream https://gecgithub01.walmart.com/platform/ms-df-es-app-configs.git
git remote -v

# You should see something like the following:
origin     https://gecgithub01.walmart.com/<YOUR-USER-ID>/ms-df-es-app-configs.git (fetch)
origin     https://gecgithub01.walmart.com/<YOUR-USER-ID>/ms-df-es-app-configs.git (push)
upstream   https://gecgithub01.walmart.com/platform/ms-df-es-app-configs.git (fetch)
upstream   https://gecgithub01.walmart.com/platform/ms-df-es-app-configs.git (push)

# If you do not see something similar to the above, then it means that you did not fork the repo but directly cloned it.
# This is not allowed and you should start reading from the top of this file and make sure you did not miss any step.
Make changes to your config. If you have a local ES on your laptop, do test the new configs there.
Run the script ruby validate-es-configs.rb your-directory-name and see if any of your files fail the validation.
cd ms-df-ES-app-configs
ruby validate-es-configs.rb <my-es-config-directory>
 
 
# Example:
ruby validate-es-configs.rb crm-qa-es-7.6.1
Send us a PR (pull request) from your repo if your configs pass the validations.
Along with the PR, also create a support ticket for us using wmlink/searchhelp describing briefly what you are doing and your team name. (Do not write "es" or "elasticsearch" as the team name. Mention "your-team-name")
