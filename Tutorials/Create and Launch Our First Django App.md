We are now going to create a very basic Django application. This will simply be the default landing page for Django that will ensure we at least are able to access this server.

## Create Our Project 
1. Create a place for our Django Projects and our first project to live.
```
cd ~
mkdir code && cd code
mkdir first_project && cd first_project
```

2. Initialize our `uv` project.
```
uv init
```

3. Install `django` into our project.
```
uv add django
```

4. Start our first django project.
```
mkdir django
uv run django-admin startproject first_project ./django
cd django
```

## Edit settings and launch the development web server
1. Edit the `settings.py` file to allow external connections
```
nano first_project/settings.py
```
- Change the value in `ALLOWED_HOSTS` to accept all incoming with the `*`
```
ALLOWED_HOSTS = ["*"]
```
* Exit nano making sure to save the modified file (Ctrl+X)

2. Run the development server.
```
uv run python manage.py runserver 0.0.0.0:8000
```

## Access the Django start page
At this point you have a web server running and should be able to access it via a web browser.

1. Access your Django instance at the external IP address followed by the port number your web server is listening on.
```
http://<ip address>:8000
```

2. You should now be greeted with a fantastic page that looks like this:
![[Pasted image 20250116213208.png]]

3. Once you have completed what you need to do with the development server be sure to shut it down. Our current setup isn't the most secure setup so we don't want to leave it available outside of our testing. Use Ctrl+C to shut down the server.