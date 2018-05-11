# CSC 519 DevOps - Project

This project consists of 4 milestones which together represent a complete DevOps pipeline. There are two web applications which are used for this pipeline viz. checkbox.io and iTrust2.

## Presentation
[<img src="https://img.youtube.com/vi/O_8tCQAwt64/0.jpg" href="Click to Watch" title="Click to Watch" height="250" width="350">](https://youtu.be/O_8tCQAwt64)

### Milestone 1: [Configuration and Build](https://github.com/omkaracharya/Complete-DevOps-Pipeline/tree/ConfigAndBuild)  
We provisioned a Jenkins server on an AWS EC2 instance. We created a build job on Jenkins server using Jenkins Job Builder. This job will perform the build commands and if successful, the post-build scripts will be run for each application. As a part of the post-build scripts, we provisioned 2 AWS EC2 instances (one for each application).

### Milestone 2: [Test and Analysis](https://github.com/omkaracharya/Complete-DevOps-Pipeline/tree/TestAnalysis)
We implemented 3 sub tasks viz. Commit Fuzzer, Test Prioritization Analyzer, and Automated Test Generation. For commit fuzzer, we used mutation-based fuzzing We made 100 different fuzzed commits and ran test suites on the code base. After those 100 runs, we prioritized the test suites based on the time required for the test each run and the number of times the test failed. These two sub tasks were focusing on iTrust application. For checkbox.io, we developed an automated test generator which generates test cases for every API route in checkbox.io.

### Milestone 3: [Deployment and Infrastructure](https://github.com/omkaracharya/Complete-DevOps-Pipeline/tree/Deployment)
We deployed iTrust using Rolling Updates strategy whereas checkbox.io using Canary Release strategy. We created a dockerized version of checkbox.io and deployed it on Kubernetes cluster. We also implemented a feature flag using Redis which will enable/disable a particular feature of checkbox.io when toggled using a simple web application.

### Milestone 4: [Special](https://github.com/omkaracharya/Complete-DevOps-Pipeline/tree/Special)
We implemented 3 sub tasks. The first one is Docker Monkey. We deployed 3 EC2 servers (one as a proxy server and 2 production servers). When the CPU usage on any of the production server exceeds the threshold, the proxy server stops forwarding requests to that server. We also included ESLint as a part of post commit hook. As the third task, we implemented a load handler which makes the production server Read-Only when it is flooded with POST requests.
