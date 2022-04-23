# CMPE 172 - Lab #10 Notes

## CI Workflow (Part 1)
Steps for what I did to accomplish part 1:
1. Click on Actions on the top bar
2. Select `Java with Gradle` -> Configure
3. Paste in code from Canvas to the `.github/workflows/gradle.yml`
4. Changed main -> master (b/c used master on initial commit)

Challenges:
- I had to cancel the workflow and restart it after ~15 minutes of the build being queued. I did this by pressing the red button for `Cancel Workflow` and then on th left side, I pressed the recycle button.

### Screenshot of output
![CI Workflow](ci-workflow.png?raw=true "CI Workflow")	


## CD Workflow (Part 2)
### Step 1 - showing files present in repo
![Step 1](step-1.png?raw=true "Step 1")	

### Step 2 - GKE Secrets
![Step 2](step-2.png?raw=true "Step 2")	
![Step 2.2](step-22.png?raw=true "Step 2.2")	

### Step 3 - Env variables
![Step 3](step-3.png?raw=true "Step 3")	

Challenges:
- Had to figure out where to make the changes to the deployment file. I had to add a new workflow -> Deployment to GKE.

### Step 4 - Trigger CD Deployment
Challenges:
- For the `GKE_SA_KEY`, I had only copied the private key, and had to google a json parsing error to find out it should have been the entire json file that was downloaded
- I ran into permission issues where the CD pipeline did not have access. I had to research into what the `container.clusters.get` permission is was and add appropriate permissions to the account specified in the json client

![Step 4.1](step-41.png?raw=true "Step 4.1")	
![Step 4.2](step-42.png?raw=true "Step 4.2")	
![Step 4.3](step-43.png?raw=true "Step 4.3")	
![Step 4.4](step-44.png?raw=true "Step 4.4")	
![Step 4.5](step-45.png?raw=true "Step 4.5")	
![Step 4.6](step-46.png?raw=true "Step 4.6")	