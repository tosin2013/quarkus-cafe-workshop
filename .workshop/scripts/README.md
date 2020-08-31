Local Deployment Steps using docker
----------------------

To build the workshop image locally using `docker` you would run:
```
docker build -t quarkus-cafe-workshop:v0.0.1 .
```

To run the image, you would then use:

```
docker run --rm -p 10080:10080 quarkus-cafe-workshop:v0.0.1 
```

Open URL in web browser

```
http://localhost:10080/dashboard/
```

Remove image 
```
docker rmi quarkus-cafe-workshop:v0.0.1
```

Personal Deployment
-------------------

If you don't want to deploy the workshop for multiple users, you can instead deploy a single instance of the workshop.

To do this, ensure that you have first deleted any spawner deployment created using the commands above.

Then run:

```
.workshop/scripts/deploy-personal.sh
```

You do not need to be cluster admin to deploy a single instance of the workshop.

If you need to deploy the workshop from the local content, as for when using the spawner, run:

```
.workshop/scripts/build-workshop.sh
```

You do not need to force a re-deployment as it will happen automatically.

To delete the workshop instance run:

```
.workshop/scripts/delete-personal.sh
```

Also run the scripts to delete the build configuration and resources.