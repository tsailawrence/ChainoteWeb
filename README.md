# ChainNoteWeb

run in docker:
```bash=
# build production file
cd frontend && yarn && yarn build && cd ..

# build a docker image
docker build -t chain-note-web .

# run on docker locally
docker run --rm --name chain-note-web -d -p 3000:3000 chain-note-web
```

when docker says that, the port 3000 is already in use:
```bash=
docker stop chain-note-web

lsof -i:3000
kill [the process pid]
```
and then restart again.

push to docker hub:
```bash=
docker tag chain-note-web <username>/chain-note-web:<version>
docker push <username>/chain-note-web:<version>
```