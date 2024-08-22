# Push your Ansible roles to Ansible Galaxy

1. Make sure your role is structured correctly. The basic structure should look like this:

```
my_role/
├── defaults/
│   └── main.yml
├── files/
├── handlers/
│   └── main.yml
├── meta/
│   └── main.yml
├── tasks/
│   └── main.yml
├── templates/
├── tests/
│   ├── inventory
│   └── test.yml
└── vars/
    └── main.yml
```

2. Make sure ansible-galaxy CLI exists

```
ansible-galaxy --version
```

3. Push Your Role to GitHub

```
cd <role-name>
git init
git remote add origin <https://github.com/your_github_username/my_role.git>
git add .
git commit -m "Initial commit"
git push -u origin main
```

4. Import the Role to Ansible Galaxy

```
ansible-galaxy role import <your_github_username> <role-name>
```
5. To run a playbook using an ansible role e.g `ansible-galaxy docker-playbook.yaml`
```
ansible-galaxy <name_of_playbook.yaml>
```
6. First, go into the role you have created e.g `httpd` and initialize a git repository
```
git init
```
7. Then, add the created repository from GitHub to the Linux server
```
git remote add origin <URL_TO_GITHUB_REPO>
```
8. Run `git remote -v` to ensure that the git repo has been added successfully, then run `git add.`,`git commit -am "add all files"` and `git push origin main`
