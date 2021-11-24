
# Creating a basic S2I builder image  

An S2I image for building shiny applications.

## Creating the application image

The application image combines the builder image with your applications source code. The following command will create the application image:

```
s2i build test/test-app rshiny-s2i:4.0.5 hello-world-rshiny:local
---> Building and installing application from source...
```

Using the logic defined in the *assemble* script, s2i will now create an application image using the builder image as a base and including the source code from the test/test-app directory. 

## Running the application image

Running the application image is as simple as invoking the docker run command:

```
docker run -d -p 3838:3838 hello-world-rshiny:local
```
