Some new developers have joined xFusionCorp Industries and have been assigned Nautilus project. They are going to start development on a new application, and some pre-requisites have been shared with the DevOps team to proceed with. Please note that all tasks need to be performed on storage server in Stratos DC.



a. Install git, set up any values for user.email and user.name globally and create a bare repository /opt/demo.git.


b. There is an update hook (to block direct pushes to the master branch) under /tmp on storage server itself; use the same to block direct pushes to the master branch in /opt/demo.git repo.


c. Clone /opt/demo.git repo in /usr/src/kodekloudrepos/demo directory.


d. Create a new branch named xfusioncorp_demo in repo that you cloned under /usr/src/kodekloudrepos directory.


e. There is a readme.md file in /tmp directory on storage server itself; copy that to the repo, add/commit in the new branch you just created, and finally push your branch to the origin.


f. Also create master branch from your branch and remember you should not be able to push to the master directly as per the hook you have set up.


```bash
# ststor01	172.16.238.15	ststor01.stratos.xfusioncorp.com	natasha	Bl@kW
ssh natasha@ststor01
git config --global --add user.name natasha
git config --global --add user.email natasha@stratos.xfusioncorp.com
git init --bare /opt/demo.git
cp /tmp/update /opt/demo.git/hooks/update
cd /usr/src/kodekloudrepos/ 
git clone /opt/demo.git
cd demo
git checkout -b xfusioncorp_demo
cp /tmp/readme.md .
git add .
git commit -m 'add readme.md'
git push origin xfusioncorp_demo
git checkout -b master
git push
```

