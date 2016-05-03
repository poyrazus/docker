# A minimal JRE 8 base image

* Based on [Alpine Linux](https://www.alpinelinux.org/) 3.3
* Added OpenJDK 8


How to build the image
-----------------
* Run the following command in the folder containing your Dockerfile. 
* Do not forget the dot at the end (implying current working directory)
* Exchange __your-repo-name__, __your-image-name__, and __your-version-name__ with the choise of yours. 

```
docker build --tag="<your-repo-name>/<your-image-name>:<your-version-name>" .
```
Example: docker build --tag="myrepo/alpine-java8:latest" .

How to test
-----------------
* Run the following two commands in the console (First command only creates a Hello World file)
```
echo 'public class Hello { public static void main(String[] args) { System.out.println("Hello World!"); } }' > Hello.java
docker run --rm -v "$(pwd)":/mnt --workdir /mnt <your-repo-name>/<your-image-name>:<your-version-name> sh -c "javac Hello.java && java Hello"
```
