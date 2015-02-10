<<<<<<< HEAD
#DeploymentUmbraco.com uses a deployment model that relies on Git, Kudu, and Courier core technology to move your changes from one environment to another.  Umbraco.com uses a classic "left to right" deployment model, meaning that changes are first made in the development environment, then deployed to the staging environment, then deployed to the live environment.  Note:  not all projects have a staging environment, so your deployment may be from development to live.##How do I deploy?When working directly with an umbraco.com project, you deploy using the "Deploy to ..." button from your project's portal.  When working locally, or in an environment outside of umbraco.com, to deploy a site to umbraco.com after you’ve made changes you execute a Git Push from your local Git client.  Umbraco keeps track of all the changes you make to a site and includes these changes when you deploy.  Of course, once you’ve deployed your local changes to your dev site on umbraco.com deploying to your staging or your live site is literally as simple a pressing the "Deploy to..." button.##I’m ready to get started, what do I do first?###Working directly in umbraco.comWhen working with your umbraco.com site directly, having logged in to the umbraco back office, any changes you make will automatically be identified and comitted to the site's Git repository.  This includes umbraco specific items like document types, but also files, and even media.  If you have more than "a few" media items see our recommendations for working with [media in umbraco.com](/setup/media.md).  As you add content and make changes in your site you'll notice that in the umbraco.com portal these changes are picked up and added to the site's Git repository.  There will be messages in the activity stream as well as an indication of how many commits have been made just above the "Deploy to ..." button.![commits](images/commits.png)###Working with a local clone of an umbraco.com siteFrom the umbraco.com portal [www.umbraco.io](www.umbraco.io) copy your dev site’s **HTTPS Clone Url** and then clone the site using your favorite Git client.  We like [SourceTree](http://www.sourcetreeapp.com/) or [Git Extensions](http://code.google.com/p/gitextensions/).  We'll use SourceTree in this example.  Here are the steps to clone your site:1. Copy the HTTPS Clone Url from the portal for your dev site![clone dialog](/images/cloneurl.png)2. From SourceTree select Clone/New and paste the Url in the Source Path box![clone dialog](/images/sourcetreeclone.png)3. Set your Destination Path to where you keep your local work4. You’ll be prompted to log in, use the same credentials as you use for the portal![clone dialog](/images/sourcetreeauth.png)5. Click CloneNow you have an exact copy of your umbraco.com dev site locally.  We like to use Microsoft WebMatrix when working locally, but you can use Visual Studio or another development tool or web server of course.  When you run your local site for the first time you’ll notice that umbraco updates the site.  Wait until this process completes as it also creates the local SqlCE database for your site.![Alt text](/images/extractingdata.png)Once your local site is running, any edits you make you make using the umbraco back office will be picked up by umbraco.  This includes umbraco items like document types and also items like CSS file you add and even your own custom dll’s.Once you have your local site just how you want it you’ll Git Commit the changes you’ve made and Git Push them to your umbraco.com site for deployment.  We’ll do this using SourceTree again.  So the steps to deploy a locally cloned umbraco.com site that has been editied locally to your umbraco.com project's dev site are:1. In SourceTree review the File Status tab and Stage all files by checking the box.  2. You can unstage any files in _/app_data/TEMP/_ , _/app_data/umbraco.sdf_, _/app_data/umbraco.config_, and other temporary files you may be using.  These files should be ignored by umbraco and your Git client as we've added a _.gitignore_ file when you first cloned your site.  But if you changed this file, you'll need to manually ignore the above directories and files.3. Select Commit and enter a commit message4. Click the Commit button5. Now select the Push option - which will have a number (of commits) displayed6. Make sure you have the master branch selected (this is the only one that will get deployed) and click the OK button7. You may wish to check the Show All Output box so that all messages from your site are displayed8. Once the push and deployment is complete you will see a Deployment Successful message in the output window9. Congratulations!  You just did a remote site deployment.Now, when you login to your dev site you’ll notice all the items you created locally are present.  You can review these updates, and make more as needed.  When you’re ready to deploy your live site, you only need to use the Deploy to Live option from the umbraco.com portal.If your deployment contains lots of changes it can take a few minutes for umbraco.com to process all of these and to create the items in your dev site.##What happens when I do a deployment?Umbraco.com deployments involve several different parts - Git, Kudu, and Courier core.  Each of these does the deployment work so you don't have to.  The process of a deployment looks like this.![deploy process](images/deployprocess.png)When you want to move changes you;ve made from one environment to another, that process is what we call a deployment. A deployment can be anything from moving a complete website into production, moving a small feature update from development to staging for QA or moving a new content section from staging to live.A deployment is initated from the umbraco.com portal by clicking the "Deploy to ..."" button for an Environment. As a part of a deployment you can create a description of the deployment for historical tracking - for instance “Rolling out the Dutch content section” - which is then shown in the project's  activity stream.##There are three types of deployments1. **Full Deployment** Move all changes from one environment to another2. **Content Deployment** Move all or some content changes. This is typically done by Content Editors making updates in the staging environment.3. **Non-Content Deployment** Move all changes, except Content. This moves Assets, Code and other file-based content from one environment to another and is typically used by Developers to add or update features.
=======
#Deployment
Umbraco.com uses a deployment model that relies on Git, Kudu, and Courier core technology to move your changes from one environment to another.  Umbraco.com uses a classic "left to right" deployment model, meaning that changes are first made in the development environment, then deployed to the staging environment, then deployed to the live environment.  

Note:  not all projects have a staging environment, so your deployment may be from development to live.

##How do I deploy?
When working directly with an umbraco.com project, you deploy using the "Deploy to ..." button from your project's portal.  

When working locally, or in an environment outside of umbraco.com, to deploy a site to umbraco.com after you’ve made changes you execute a Git Push from your local Git client.  Umbraco keeps track of all the changes you make to a site and includes these changes when you deploy.  Of course, once you’ve deployed your local changes to your dev site on umbraco.com deploying to your staging or your live site is literally as simple a pressing the "Deploy to..." button.

##I’m ready to get started, what do I do first?
###Working directly in umbraco.com
When working with your umbraco.com site directly, having logged in to the umbraco back office, any changes you make will automatically be identified and comitted to the site's Git repository.  This includes umbraco specific items like document types, but also files, and even media.  If you have more than "a few" media items see our recommendations for working with [media in umbraco.com](/setup/media.md).  As you add content and make changes in your site you'll notice that in the umbraco.com portal these changes are picked up and added to the site's Git repository.  There will be messages in the activity stream as well as an indication of how many commits have been made just above the "Deploy to ..." button.

![commits](images/commits.png)

###Working with a local clone of an umbraco.com site
From the umbraco.com portal [www.umbraco.io](www.umbraco.io) copy your dev site’s **HTTPS Clone Url** and then clone the site using your favorite Git client.  We like [SourceTree](http://www.sourcetreeapp.com/) or [Git Extensions](http://code.google.com/p/gitextensions/).  We'll use SourceTree in this example.  Here are the steps to clone your site:

1. Copy the HTTPS Clone Url from the portal for your dev site
![clone dialog](images/cloneurl.png)
2. From SourceTree select Clone/New and paste the Url in the Source Path box
![clone dialog](images/sourcetreeclone.png)
3. Set your Destination Path to where you keep your local work
4. You’ll be prompted to log in, use the same credentials as you use for the portal
![clone dialog](images/sourcetreeauth.png)
5. Click Clone

Now you have an exact copy of your umbraco.com dev site locally.  We like to use Microsoft WebMatrix when working locally, but you can use Visual Studio or another development tool or web server of course.  When you run your local site for the first time you’ll notice that umbraco updates the site.  Wait until this process completes as it also creates the local SqlCE database for your site.

![Alt text](/images/extractingdata.png)

Once your local site is running, any edits you make you make using the umbraco back office will be picked up by umbraco.  This includes umbraco items like document types and also items like CSS file you add and even your own custom dll’s.

Once you have your local site just how you want it you’ll Git Commit the changes you’ve made and Git Push them to your umbraco.com site for deployment.  We’ll do this using SourceTree again.  So the steps to deploy a locally cloned umbraco.com site that has been editied locally to your umbraco.com project's dev site are:

1. In SourceTree review the File Status tab and Stage all files by checking the box.  
2. You can unstage any files in _/app_data/TEMP/_ , _/app_data/umbraco.sdf_, _/app_data/umbraco.config_, and other temporary files you may be using.  These files should be ignored by umbraco and your Git client as we've added a _.gitignore_ file when you first cloned your site.  But if you changed this file, you'll need to manually ignore the above directories and files.
3. Select Commit and enter a commit message
4. Click the Commit button
5. Now select the Push option - which will have a number (of commits) displayed
6. Make sure you have the master branch selected (this is the only one that will get deployed) and click the OK button
7. You may wish to check the Show All Output box so that all messages from your site are displayed
8. Once the push and deployment is complete you will see a Deployment Successful message in the output window
9. Congratulations!  You just did a remote site deployment.

Now, when you login to your dev site you’ll notice all the items you created locally are present.  You can review these updates, and make more as needed.  When you’re ready to deploy your live site, you only need to use the Deploy to Live option from the umbraco.com portal.

If your deployment contains lots of changes it can take a few minutes for umbraco.com to process all of these and to create the items in your dev site.

##What happens when I do a deployment?
Umbraco.com deployments involve several different parts - Git, Kudu, and Courier core.  Each of these does the deployment work so you don't have to.  The process of a deployment looks like this:





>>>>>>> aa4c8367c7b52bc0048be032be58d3df6af1dbc0
