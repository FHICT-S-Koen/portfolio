# Secure Docker containers - research

## Main question
How to make a Docker container as secure as possible?

## Sub-questions
1. How can image hardening help with security?
    - What is image hardening?
    - How would you harden your image?
2. How do you securely pass secrets to your container?
    - What are the conventional ways of passing secrets to your container?
    - Can you safely pass secrets to your container by using build arguments?

## Strategy & Method
- Strategy: Library
- Method: Literature study

## Answers
### 1. Image hardening
To understand what the hardening of a Docker image is, we first should address what exactly Docker images and containers are and what it means to harden something.

Going by a quick and simple explanation a Docker image is more or less an instruction manual, telling your system how to create your Docker container. To get an image you can either get an image and use it as is (from [docker hub](https://hub.docker.com/)) or make your own, by basing it of of another so called "base image". After you got your image you can create a Docker container that can run your application inside of it. By doing this you always have a production ready version of your application that is also easy to deploy and distribute.<sup>[1](#Sources)</sup>

Then what does hardening something mean? Hardening (in computing) usually refers to the process of making a system more secure by reducing vulnerabilities, depending on how many functions the system serves. The more functions a system has the more vulnerabilities one may come across. So to mitigate vulnerabilities you want to remove as much unnecessary software or so called security risks to mitigate vulnerabilities. This also includes things like: changing default passwords, getting rid of unnecessary logins, and disabling or removing unnecessary services.<sup>[2](#Sources)</sup>
<!-- 
Starting of with image: a Docker image is a template that can only be read and contains a set of instructions to create a Docker container. A Docker container makes it more convenient to package your application into a production ready enviorment and distrbute it. By having its own little operation system that contains your application and makes it easy to distribute   -->

Now then how would you harden your images? I have compiled a list of the most commonly talked about ways to better secure your Docker images in the following paragraphs.

**Minimal base image**

Starting of with using minimal base images. Most people starting of with Docker will use something like node as their quick and easy way to make sure all the right packages can be installed that their applications can be build for production and run with npm. This however ends up exposing your application to a load of vulnerabilities and you can compare it to using a full blown operating system. By doing this you end up adding unnecessary security risks from the start. By using a minimal base image that can only do the bare minimum to get your application up and running will minimize the attack surface for attackers. To give an example of a commonly used minimal base image that also has many variants and flavors of what you need are Alpine images. Those images are a super light weight flavor of Linux and are a great starting point. However if you really want the best of the best you can use images that don't even have a shell and can only execute things like binary files. When getting into this territory you still need to build your image and you don't want to add unnecessary packages to build your application. This is when you get into Multi-stage builds which is the next topic.

**Multi-stage builds**

Multi stage builds essentially exist out of a build stage which first uses an image that has the necessary tools and libraries to run the needed commands. Then after your build stage is done you pull another image this time much smaller that only can start your application containing only the necessary build files from the previous image. This is the optimal way of minimizing your (final) Docker image. This not only makes 

<!-- 2. Least privileged user
3. Sign and verify images to mitigate MITM attacks
4. Find, fix and monitor for open source vulnerabilities
5. Don’t leak sensitive information to Docker images
6. Use fixed tags for immutability
7. Use COPY instead of ADD
8. Use metadata labels
10. Use a linter -->

### 2. Securely passing secrets


## Conclusion

## Sources
1. [Beginners guide to understanding and building Docker images](https://jfrog.com/knowledge-base/a-beginners-guide-to-understanding-and-building-Docker-images/)
2. [General explanation of what hardening means in computing](https://en.wikipedia.org/wiki/Hardening_(computing))
3. [10 Docker Security Best Practices](https://snyk.io/blog/10-Docker-image-security-best-practices/)