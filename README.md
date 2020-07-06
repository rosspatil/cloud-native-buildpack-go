# cloud-native-buildpack-go
This is a GoLang builder using Cloud Native buildpacks

You can create your custom Cloud Native buildpacks by taking the help of this example repository.

Folowing command makes you use this builder -
```
pack build --builder roshanpatil/cnb-go-builder:alpine <container image name>
```

This builder uses customized stack image by me - 
```
run-image: roshanpatil/cnb-base-image:alpine
build-image: roshanpatil/cnb-base-image:alpine
```