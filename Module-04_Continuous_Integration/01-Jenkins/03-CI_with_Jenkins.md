# Continous Integration with Jenkins

## Different ways of Integrating Jenkins with Github repos (remote)

### 1. Using `Poll SCM`

- Jenkins will keep polling to your github repos to check if there is any new check-ins.

### 2. Using `Github Webhooks`

- Jenkins will listen to a webhook and GitHub will let jenkins know if there are any new check-ins.

## `Lab-01`: Create your first Jenkins job (hello world)

### 00-Prerequisites

- Fully configured Jenkins server. For more details, follow [Jenkins installation lab](02-Jenkins_Installation.md)

### Step-01: Install Jenkins Git plugin if not present

### Step-02: Create a new GitHub repository (private)

### Step-03: Check-in the application code into GitHub repos

### Step-04: Create your first build job (freestyle) in Jenkins

- Sign-in to your Jenkins server
- Click on **New Item link** from the jenkins dashboard.
- Item Name: FirstJenkinsJob
- Type: Freestyle Project
- Under General tab:
  - Description: Hello world job
  - Under Build section >> Add build step >> Execute shell
  ```
  echo "hello world"
  uptime
  ```
- Click on **Apply** button and then **Save**

### Step-05: Execute the Jenkins job created in previous step

- Navigate to the job that you just created >> Click **Build now**.
- Verify the output message from the **Console Output** section.

## `Lab-02`: Integrate Jenkins with Git using SCM Poll mechanism

### Step-01: Install Git on Jenkins server

```
# update the hostname of your jenkins server
hostname JenkinsServer

# INFO: In order to make the hostname update permanently, update the hostname in /etc/hostname

# Install Git
sudo yum install -y git

# After Git installation, check the git version to confirm the installation
git --version
```

### Step-02: Install GitHub plugin on Jenkins server

- Navigate to **Manage Jenkins** section >> **Manage Plugins**
- Select the **Available** tab >> Search for **GitHub plugin** >> **Install without restart**

### Step-03: Configure Git on Jenkins server

- Navigate to **Manage Jenkins** section >> **Global Tools Configuration**
- Go to Git section
  Name: <label>
  Path to Git: <path_of_git_executable>

## `Lab-03`: Integrate Jenkins with Git using Webhooks

### Step-01: go to your GitHub repository and click on **Settings**.

### Step-02: Click on Webhooks and then click on **Add webhook**.
