# Secure docker containers - research

## Main question
How to make a docker container as secure as possible?

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
To understand what the hardening of a docker image is, we first should address what it means to harden something. 

The meaning of hardening (in computing) usually refers to the process of making a system more secure by reducing vulnerabilities, depending on how many functions the system serves. The more functions a system has the more vulnerabilities one may come across. So to mitigate vulnerabilities you mostly want to remove as much unnecessary software or so called security risks to mitigate vulnerabilities. Other ways of reducing security risks are changing default passwords, getting rid of unnecessary logins, and disabling or removing unnecessary services.<sup>[1](#Sources)</sup>

Now then how would you harden your images. 

### 2. Securely passing secrets


## Conclusion

## Sources
1. [General explanation of what hardening means in computing](https://en.wikipedia.org/wiki/Hardening_(computing))
2. [10 Docker Security Best Practices](https://snyk.io/blog/10-docker-image-security-best-practices/)