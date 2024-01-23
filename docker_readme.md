# Use Docker to preview changes to the Hugo site before commiting it

Using HugoMods
https://hugomods.com/en/docs/docker/
https://github.com/hugomods/docker

Pull the docker image if you haven't done so before (i.e. `docker pull hugomods/hugo`)

Go to the current working directory to your website project root.
e.g. `cd ~/Github/mcx-lab.github.io/`

Then start the Hugo server
```
docker run -it --rm -p 8080:8080 \
  -v ${PWD}:/src \
  --user 1000:1000 \
  hugomods/hugo \
  hugo server --bind 0.0.0.0 -p 8080
```

You should be able to see a local version of the site at http://localhost:8080/ (bind address 0.0.0.0)

Any changes made to the working directory should be reflected in the local site immediately.


