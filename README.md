# Running it on Docker

> This was created for educational purposes mainly, ie me getting to understand Docker and how to create images from a github project.

Then you can rebuild the docker image and then deploy as needed. Go into the project folder where the dockerfile is located and run this.  
`docker build -t appname .`

This docker image was created in such a way, to allow for adding the Markdown files for the <strong>blogs</strong> and <strong>projects</strong> locally in your docker host machine. This is achieved by created a symlink between the container folder and the host system.

In the "docker run" command below you will see:  
Both the part in bold will need to be replaced with a location in your local machine.You can create a folder for each and then use `pwd` command in your terminal to find the location, after your created

- -v <strong>/path/to/blogs</strong>:/app/api/content/posts \
- -v <strong>/path/to/projects</strong>:/app/api/content/projects \

### docker cli ([click here for more info](https://docs.docker.com/engine/reference/commandline/cli/))

```bash
docker run -d \
  --name=flask-portfolio \
  -p 5002:5000 \
  -v /path/to/blogs:/app/api/content/posts \
  -v /path/to/projects:/app/api/content/projects \
  --restart unless-stopped \
  buildwithdan/flask-portfolio

```
