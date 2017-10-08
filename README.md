# whitespace-filter
This filter is designed to remove white spaces (minify) HTML, CSS, and JS depending on the options enabled in the application initialization.

## Requirements
I used the last version of [htmlcompressor](https://code.google.com/archive/p/htmlcompressor/) to build the project. The latest version 
is [1.5.3](https://storage.googleapis.com/google-code-archive-downloads/v2/code.google.com/htmlcompressor/htmlcompressor-1.5.3.zip). You
will need to install it in your local Maven repository since it is not in the public repositories.

### jar
```bash
mvn deploy:deploy-file -DgroupId=com.googlecode.htmlcompressor \
-DartifactId=htmlcompressor -Dversion=1.5.3 \
-Dfile=htmlcompressor-1.5.3.jar \
-Dpackaging=jar \
-Durl=file:///PATH_TO_LOCAL_REPOSITORY/.m2/repository
```
### sources
```bash
mvn deploy:deploy-file -DgroupId=com.googlecode.htmlcompressor \
-DartifactId=htmlcompressor -Dversion=1.5.3 \
-Dfile=htmlcompressor-1.5.3-sources.jar \
-Dpackaging=jar \
-Durl=file:///PATH_TO_LOCAL_REPOSITORY/.m2/repository \
-Dclassifier=sources
```
### javadocs
```bash
mvn deploy:deploy-file -DgroupId=com.googlecode.htmlcompressor \
-DartifactId=htmlcompressor -Dversion=1.5.3 \
-Dfile=htmlcompressor-1.5.3-javadoc.jar \
-Dpackaging=jar \
-Durl=file:///PATH_TO_LOCAL_REPOSITORY/.m2/repository \
-Dclassifier=javadoc
```
### Maven Dependency
```xml
<dependency>
    <groupId>com.googlecode.htmlcompressor</groupId>
    <artifactId>htmlcompressor</artifactId>
    <version>1.5.3</version>
</dependency>
```
## Usage
This filter is an automatic filter based on its annotations, you simply need to add it to your project.
```xml
<dependency>
    <groupId>com.bluelotussoftware</groupId>
    <artifactId>whitespace-filter</artifactId>
    <version>1.0.0</version>
</dependency>
```
parameter name | parameter value (default) | description
------------------------- | ------------------------- | -------------------------
compressCss | true | Enable compression of CSS.
compressJs     | true | Enable compression of JS.
removeIntertagSpaces | true | Enable removal of inter-tag spaces.

If any of the default values must be overridden, you may use the **web.xml**, or another alternative mechanism.
