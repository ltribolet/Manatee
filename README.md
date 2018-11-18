# Manatee

## Setup
### Tools
In order to use this you have to clone it then:
```
docker build -t manatee/tools build/tools
```

This will give the base to use either composer or npm/yarn.

### Your Environment
You can now use the `project` folder for your application either by creating a project from composer, cloning a repo, or starting your own.
It's important to keep `project` as a name if you don't want to modify all the references.

#### Composer
```
 docker run --rm --interactive --tty --volume $PWD:/app manatee/tools composer create-project symfony/website-skeleton project --ignore-platform-reqs
```
```
 winpty docker run --rm --interactive --tty --volume  "/$(pwd)":/app:Z manatee/tools composer create-project symfony/website-skeleton project --ignore-platform-reqs
```
#### Cloning
```
git clone <URL> project
```
#### Symlink
```
ln -s <source> ./project
```

### Version
Once created you can start versioning it if it's not already the case:
```
cd project && git init
```

### Hosts
You need to add the following to your hosts file:
```
127.0.0.1 project.localhost
```

### DB
Copy `.env.example` content to `project/.env` file that you have from your project. Update it from your project value.

## Run
```
docker-compose up
```

Go at http://project.localhost
