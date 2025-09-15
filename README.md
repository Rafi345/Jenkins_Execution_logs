Started by user SK RAFI
Obtained Jenkinsfile from git https://github.com/Rafi345/Book-My-Show
[Pipeline] Start of Pipeline
[Pipeline] node
Running on Jenkins in /var/lib/jenkins/workspace/Rafi/pipeline-1
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Declarative: Checkout SCM)
[Pipeline] checkout
Selected Git installation does not exist. Using Default
The recommended git tool is: NONE
No credentials specified
 > git rev-parse --resolve-git-dir /var/lib/jenkins/workspace/Rafi/pipeline-1/.git # timeout=10
Fetching changes from the remote Git repository
 > git config remote.origin.url https://github.com/Rafi345/Book-My-Show # timeout=10
Fetching upstream changes from https://github.com/Rafi345/Book-My-Show
 > git --version # timeout=10
 > git --version # 'git version 2.43.0'
 > git fetch --tags --force --progress -- https://github.com/Rafi345/Book-My-Show +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git rev-parse refs/remotes/origin/feature/update-readme^{commit} # timeout=10
Checking out Revision be9a0fea5b247abaf95e5c5238f144fa4273339d (refs/remotes/origin/feature/update-readme)
 > git config core.sparsecheckout # timeout=10
 > git checkout -f be9a0fea5b247abaf95e5c5238f144fa4273339d # timeout=10
Commit message: "Changed email in Jenkinsfile"
 > git rev-list --no-walk be9a0fea5b247abaf95e5c5238f144fa4273339d # timeout=10
[Pipeline] }
[Pipeline] // stage
[Pipeline] withEnv
[Pipeline] {
[Pipeline] tool
[Pipeline] withEnv
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Declarative: Tool Install)
[Pipeline] tool
[Pipeline] envVarsForTool
[Pipeline] }
[Pipeline] // stage
[Pipeline] withEnv
[Pipeline] {
[Pipeline] stage
[Pipeline] { (Clean Workspace)
[Pipeline] tool
[Pipeline] envVarsForTool
[Pipeline] withEnv
[Pipeline] {
[Pipeline] cleanWs
[WS-CLEANUP] Deleting project workspace...
[WS-CLEANUP] Deferred wipeout is used...
[WS-CLEANUP] done
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Checkout from Git)
[Pipeline] tool
[Pipeline] envVarsForTool
[Pipeline] withEnv
[Pipeline] {
[Pipeline] git
Selected Git installation does not exist. Using Default
The recommended git tool is: NONE
No credentials specified
Cloning the remote Git repository
Cloning repository https://github.com/Rafi345/Book-My-Show.git
 > git init /var/lib/jenkins/workspace/Rafi/pipeline-1 # timeout=10
Fetching upstream changes from https://github.com/Rafi345/Book-My-Show.git
 > git --version # timeout=10
 > git --version # 'git version 2.43.0'
 > git fetch --tags --force --progress -- https://github.com/Rafi345/Book-My-Show.git +refs/heads/*:refs/remotes/origin/* # timeout=10
 > git config remote.origin.url https://github.com/Rafi345/Book-My-Show.git # timeout=10
 > git config --add remote.origin.fetch +refs/heads/*:refs/remotes/origin/* # timeout=10
Avoid second fetch
 > git rev-parse refs/remotes/origin/feature/update-readme^{commit} # timeout=10
Checking out Revision be9a0fea5b247abaf95e5c5238f144fa4273339d (refs/remotes/origin/feature/update-readme)
 > git config core.sparsecheckout # timeout=10
 > git checkout -f be9a0fea5b247abaf95e5c5238f144fa4273339d # timeout=10
 > git branch -a -v --no-abbrev # timeout=10
 > git checkout -b feature/update-readme be9a0fea5b247abaf95e5c5238f144fa4273339d # timeout=10
Commit message: "Changed email in Jenkinsfile"
[Pipeline] sh
+ ls -la
total 76
drwxr-xr-x 4 jenkins jenkins  4096 Sep 14 14:47 .
drwxr-xr-x 7 jenkins jenkins  4096 Sep 14 14:47 ..
drwxr-xr-x 8 jenkins jenkins  4096 Sep 14 14:47 .git
-rw-r--r-- 1 jenkins jenkins 30439 Sep 14 14:47 BMS-Document.txt
-rw-r--r-- 1 jenkins jenkins  3369 Sep 14 14:47 Jenkinsfile
-rw-r--r-- 1 jenkins jenkins  3545 Sep 14 14:47 Jenkinsfile-30
-rw-r--r-- 1 jenkins jenkins  3669 Sep 14 14:47 Jenkinsfile1
-rw-r--r-- 1 jenkins jenkins  3991 Sep 14 14:47 Jenkinsfile2
-rw-r--r-- 1 jenkins jenkins    24 Sep 14 14:47 README.md
drwxr-xr-x 4 jenkins jenkins  4096 Sep 14 14:47 bookmyshow-app
-rw-r--r-- 1 jenkins jenkins   431 Sep 14 14:47 deployment.yml
-rw-r--r-- 1 jenkins jenkins   238 Sep 14 14:47 service.yml
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (SonarQube Analysis)
[Pipeline] tool
[Pipeline] envVarsForTool
[Pipeline] withEnv
[Pipeline] {
[Pipeline] withSonarQubeEnv
Injecting SonarQube environment variables using the configuration: sonar-server
[Pipeline] {
[Pipeline] sh
+ /var/lib/jenkins/tools/hudson.plugins.sonar.SonarRunnerInstallation/sonar-scanner/bin/sonar-scanner -Dsonar.projectName=bookmyshow -Dsonar.projectKey=bookmyshow
14:47:19.227 INFO  Scanner configuration file: /var/lib/jenkins/tools/hudson.plugins.sonar.SonarRunnerInstallation/sonar-scanner/conf/sonar-scanner.properties
14:47:19.236 INFO  Project root configuration file: NONE
14:47:19.262 INFO  SonarScanner CLI 7.2.0.5079
14:47:19.264 INFO  Linux 6.14.0-1012-aws amd64
14:47:21.248 INFO  Communicating with SonarQube Server 9.9.8.100196
14:47:22.308 INFO  Load global settings
14:47:22.447 INFO  Load global settings (done) | time=139ms
14:47:22.450 INFO  Server id: 147B411E-AZlDU040JKYn0EwmbbMj
14:47:22.455 INFO  User cache: /var/lib/jenkins/.sonar/cache
14:47:22.460 INFO  Load/download plugins
14:47:22.460 INFO  Load plugins index
14:47:22.526 INFO  Load plugins index (done) | time=66ms
14:47:22.744 INFO  Load/download plugins (done) | time=284ms
14:47:23.979 INFO  Process project properties
14:47:23.980 INFO  Process project properties (done) | time=1ms
14:47:23.988 INFO  Execute project builders
14:47:23.992 INFO  Execute project builders (done) | time=4ms
14:47:23.998 INFO  Project key: bookmyshow
14:47:23.999 INFO  Base dir: /var/lib/jenkins/workspace/Rafi/pipeline-1
14:47:23.999 INFO  Working dir: /var/lib/jenkins/workspace/Rafi/pipeline-1/.scannerwork
14:47:24.016 INFO  Load project settings for component key: 'bookmyshow'
14:47:24.046 INFO  Load project settings for component key: 'bookmyshow' (done) | time=30ms
14:47:24.393 INFO  Auto-configuring with CI 'Jenkins'
14:47:24.402 INFO  Load quality profiles
14:47:24.542 INFO  Load quality profiles (done) | time=140ms
14:47:24.547 INFO  Load active rules
14:47:26.793 INFO  Load active rules (done) | time=2246ms
14:47:26.806 INFO  Load analysis cache
14:47:26.896 INFO  Load analysis cache | time=90ms
14:47:27.044 INFO  Load project repositories
14:47:27.104 INFO  Load project repositories (done) | time=60ms
14:47:27.199 INFO  Indexing files...
14:47:27.201 INFO  Project configuration:
14:47:27.868 INFO  108 files indexed
14:47:27.869 INFO  0 files ignored because of scm ignore settings
14:47:27.871 INFO  Quality profile for css: Sonar way
14:47:27.871 INFO  Quality profile for js: Sonar way
14:47:27.871 INFO  Quality profile for json: Sonar way
14:47:27.871 INFO  Quality profile for web: Sonar way
14:47:27.871 INFO  Quality profile for yaml: Sonar way
14:47:27.871 INFO  ------------- Run sensors on module bookmyshow
14:47:28.091 INFO  Load metrics repository
14:47:28.139 INFO  Load metrics repository (done) | time=49ms
14:47:31.115 INFO  Sensor JaCoCo XML Report Importer [jacoco]
14:47:31.117 INFO  'sonar.coverage.jacoco.xmlReportPaths' is not defined. Using default locations: target/site/jacoco/jacoco.xml,target/site/jacoco-it/jacoco.xml,build/reports/jacoco/test/jacocoTestReport.xml
14:47:31.118 INFO  No report imported, no coverage information will be imported by JaCoCo XML Report Importer
14:47:31.118 INFO  Sensor JaCoCo XML Report Importer [jacoco] (done) | time=4ms
14:47:31.119 INFO  Sensor IaC CloudFormation Sensor [iac]
14:47:31.565 INFO  0 source files to be analyzed
14:47:31.648 INFO  0/0 source files have been analyzed
14:47:31.648 INFO  Sensor IaC CloudFormation Sensor [iac] (done) | time=530ms
14:47:31.648 INFO  Sensor IaC Kubernetes Sensor [iac]
14:47:31.775 INFO  2 source files to be analyzed
14:47:31.989 INFO  2/2 source files have been analyzed
14:47:31.989 INFO  Sensor IaC Kubernetes Sensor [iac] (done) | time=341ms
14:47:31.989 INFO  Sensor JavaScript analysis [javascript]
14:47:36.968 WARN  Node.js version 24 is not recommended, you might experience issues. Please use a recommended version of Node.js [16, 18]
14:47:36.988 INFO  62 source files to be analyzed
14:47:42.658 INFO  62/62 source files have been analyzed
14:47:42.658 INFO  Hit the cache for 0 out of 62
14:47:42.661 INFO  Miss the cache for 62 out of 62: ANALYSIS_MODE_INELIGIBLE [62/62]
14:47:42.661 INFO  Sensor JavaScript analysis [javascript] (done) | time=10672ms
14:47:42.661 INFO  Sensor TypeScript analysis [javascript]
14:47:42.662 INFO  No input files found for analysis
14:47:42.662 INFO  Hit the cache for 0 out of 0
14:47:42.662 INFO  Miss the cache for 0 out of 0
14:47:42.662 INFO  Sensor TypeScript analysis [javascript] (done) | time=1ms
14:47:42.662 INFO  Sensor JavaScript inside YAML analysis [javascript]
14:47:42.663 INFO  No input files found for analysis
14:47:42.664 INFO  Hit the cache for 0 out of 0
14:47:42.664 INFO  Miss the cache for 0 out of 0
14:47:42.664 INFO  Sensor JavaScript inside YAML analysis [javascript] (done) | time=2ms
14:47:42.664 INFO  Sensor CSS Rules [javascript]
14:47:42.673 INFO  17 source files to be analyzed
14:47:43.050 INFO  17/17 source files have been analyzed
14:47:43.050 INFO  Hit the cache for 0 out of 0
14:47:43.050 INFO  Miss the cache for 0 out of 0
14:47:43.050 INFO  Sensor CSS Rules [javascript] (done) | time=386ms
14:47:43.050 INFO  Sensor CSS Metrics [javascript]
14:47:43.150 INFO  Sensor CSS Metrics [javascript] (done) | time=100ms
14:47:43.150 INFO  Sensor C# Project Type Information [csharp]
14:47:43.152 INFO  Sensor C# Project Type Information [csharp] (done) | time=2ms
14:47:43.152 INFO  Sensor C# Analysis Log [csharp]
14:47:43.185 INFO  Sensor C# Analysis Log [csharp] (done) | time=33ms
14:47:43.186 INFO  Sensor C# Properties [csharp]
14:47:43.186 INFO  Sensor C# Properties [csharp] (done) | time=0ms
14:47:43.186 INFO  Sensor HTML [web]
14:47:43.228 INFO  Sensor HTML [web] (done) | time=42ms
14:47:43.228 INFO  Sensor TextAndSecretsSensor [text]
14:47:43.239 INFO  84 source files to be analyzed
14:47:43.847 INFO  84/84 source files have been analyzed
14:47:43.847 INFO  Sensor TextAndSecretsSensor [text] (done) | time=619ms
14:47:43.847 INFO  Sensor VB.NET Project Type Information [vbnet]
14:47:43.848 INFO  Sensor VB.NET Project Type Information [vbnet] (done) | time=1ms
14:47:43.848 INFO  Sensor VB.NET Analysis Log [vbnet]
14:47:43.887 INFO  Sensor VB.NET Analysis Log [vbnet] (done) | time=39ms
14:47:43.887 INFO  Sensor VB.NET Properties [vbnet]
14:47:43.887 INFO  Sensor VB.NET Properties [vbnet] (done) | time=0ms
14:47:43.887 INFO  Sensor IaC Docker Sensor [iac]
14:47:43.893 INFO  1 source file to be analyzed
14:47:43.966 INFO  1/1 source file has been analyzed
14:47:43.967 INFO  Sensor IaC Docker Sensor [iac] (done) | time=80ms
14:47:43.976 INFO  ------------- Run sensors on project
14:47:44.043 INFO  Sensor Analysis Warnings import [csharp]
14:47:44.044 INFO  Sensor Analysis Warnings import [csharp] (done) | time=1ms
14:47:44.044 INFO  Sensor Zero Coverage Sensor
14:47:44.067 INFO  Sensor Zero Coverage Sensor (done) | time=23ms
14:47:44.093 INFO  CPD Executor 10 files had no CPD blocks
14:47:44.184 INFO  CPD Executor Calculating CPD for 53 files
14:47:44.240 INFO  CPD Executor CPD calculation finished (done) | time=55ms
14:47:44.356 INFO  Analysis report generated in 100ms, dir size=722.1 kB
14:47:44.523 INFO  Analysis report compressed in 166ms, zip size=411.4 kB
14:47:44.554 INFO  Analysis report uploaded in 31ms
14:47:44.556 INFO  ANALYSIS SUCCESSFUL, you can find the results at: http://35.181.59.175:9000/dashboard?id=bookmyshow
14:47:44.556 INFO  Note that you will be able to access the updated dashboard once the server has processed the submitted analysis report
14:47:44.556 INFO  More about the report processing at http://35.181.59.175:9000/api/ce/task?id=AZlIsjyjbifAJc58GqrJ
14:47:45.190 INFO  Analysis total time: 22.061 s
14:47:45.192 INFO  EXECUTION SUCCESS
14:47:45.193 INFO  Total time: 26.053s
[Pipeline] }
[Pipeline] // withSonarQubeEnv
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Quality Gate)
[Pipeline] tool
[Pipeline] envVarsForTool
[Pipeline] withEnv
[Pipeline] {
[Pipeline] script
[Pipeline] {
[Pipeline] waitForQualityGate
Checking status of SonarQube task 'AZlIsjyjbifAJc58GqrJ' on server 'sonar-server'
SonarQube task 'AZlIsjyjbifAJc58GqrJ' status is 'IN_PROGRESS'
SonarQube task 'AZlIsjyjbifAJc58GqrJ' status is 'SUCCESS'
SonarQube task 'AZlIsjyjbifAJc58GqrJ' completed. Quality gate is 'OK'
[Pipeline] }
[Pipeline] // script
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Install Dependencies)
[Pipeline] tool
[Pipeline] envVarsForTool
[Pipeline] withEnv
[Pipeline] {
[Pipeline] sh
+ cd bookmyshow-app
+ ls -la
total 1584
drwxr-xr-x 4 jenkins jenkins    4096 Sep 14 14:47 .
drwxr-xr-x 5 jenkins jenkins    4096 Sep 14 14:47 ..
-rw-r--r-- 1 jenkins jenkins     966 Sep 14 14:47 Dockerfile
-rw-r--r-- 1 jenkins jenkins    3369 Sep 14 14:47 README.md
-rw-r--r-- 1 jenkins jenkins 1592100 Sep 14 14:47 package-lock.json
-rw-r--r-- 1 jenkins jenkins    1422 Sep 14 14:47 package.json
drwxr-xr-x 3 jenkins jenkins    4096 Sep 14 14:47 public
drwxr-xr-x 7 jenkins jenkins    4096 Sep 14 14:47 src
+ [ -f package.json ]
+ rm -rf node_modules package-lock.json
+ npm install
npm warn ERESOLVE overriding peer dependency
npm warn ERESOLVE overriding peer dependency
npm warn ERESOLVE overriding peer dependency
npm warn deprecated @npmcli/move-file@1.1.2: This functionality has been moved to @npmcli/fs
npm warn deprecated inflight@1.0.6: This module is not supported, and leaks memory. Do not use it. Check out lru-cache if you want a good and tested way to coalesce async requests by a key value, which is much more comprehensive and powerful.
npm warn deprecated move-concurrently@1.0.1: This package is no longer supported.
npm warn deprecated stable@0.1.8: Modern JS already guarantees Array#sort() is a stable sort, so this library is deprecated. See the compatibility table on MDN: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort#browser_compatibility
npm warn deprecated source-map-url@0.4.1: See https://github.com/lydell/source-map-url#deprecated
npm warn deprecated flatten@1.0.3: flatten is deprecated in favor of utility frameworks such as lodash.
npm warn deprecated @babel/plugin-proposal-private-methods@7.18.6: This proposal has been merged to the ECMAScript standard and thus this plugin is no longer maintained. Please use @babel/plugin-transform-private-methods instead.
npm warn deprecated @babel/plugin-proposal-numeric-separator@7.18.6: This proposal has been merged to the ECMAScript standard and thus this plugin is no longer maintained. Please use @babel/plugin-transform-numeric-separator instead.
npm warn deprecated @babel/plugin-proposal-nullish-coalescing-operator@7.18.6: This proposal has been merged to the ECMAScript standard and thus this plugin is no longer maintained. Please use @babel/plugin-transform-nullish-coalescing-operator instead.
npm warn deprecated @babel/plugin-proposal-class-properties@7.18.6: This proposal has been merged to the ECMAScript standard and thus this plugin is no longer maintained. Please use @babel/plugin-transform-class-properties instead.
npm warn deprecated figgy-pudding@3.5.2: This module is no longer supported.
npm warn deprecated @hapi/topo@3.1.6: This version has been deprecated and is no longer supported or maintained
npm warn deprecated @hapi/bourne@1.3.2: This version has been deprecated and is no longer supported or maintained
npm warn deprecated rollup-plugin-terser@5.3.1: This package has been deprecated and is no longer maintained. Please use @rollup/plugin-terser
npm warn deprecated rimraf@2.7.1: Rimraf versions prior to v4 are no longer supported
npm warn deprecated rimraf@2.7.1: Rimraf versions prior to v4 are no longer supported
npm warn deprecated rimraf@2.7.1: Rimraf versions prior to v4 are no longer supported
npm warn deprecated rimraf@2.7.1: Rimraf versions prior to v4 are no longer supported
npm warn deprecated urix@0.1.0: Please see https://github.com/lydell/urix#deprecated
npm warn deprecated @humanwhocodes/config-array@0.5.0: Use @eslint/config-array instead
npm warn deprecated copy-concurrently@1.0.5: This package is no longer supported.
npm warn deprecated lodash.template@4.5.0: This package is deprecated. Use https://socket.dev/npm/package/eta instead.
npm warn deprecated abab@2.0.6: Use your platform's native atob() and btoa() methods instead
npm warn deprecated rimraf@3.0.2: Rimraf versions prior to v4 are no longer supported
npm warn deprecated @babel/plugin-proposal-optional-chaining@7.21.0: This proposal has been merged to the ECMAScript standard and thus this plugin is no longer maintained. Please use @babel/plugin-transform-optional-chaining instead.
npm warn deprecated @babel/plugin-proposal-private-property-in-object@7.21.11: This proposal has been merged to the ECMAScript standard and thus this plugin is no longer maintained. Please use @babel/plugin-transform-private-property-in-object instead.
npm warn deprecated resolve-url@0.2.1: https://github.com/lydell/resolve-url#deprecated
npm warn deprecated glob@7.2.3: Glob versions prior to v9 are no longer supported
npm warn deprecated source-map-resolve@0.5.3: See https://github.com/lydell/source-map-resolve#deprecated
npm warn deprecated querystring@0.2.1: The querystring API is considered Legacy. new code should use the URLSearchParams API instead.
npm warn deprecated domexception@2.0.1: Use your platform's native DOMException instead
npm warn deprecated w3c-hr-time@1.0.2: Use your platform's native performance.now() and performance.timeOrigin.
npm warn deprecated q@1.5.1: You or someone you depend on is using Q, the JavaScript Promise library that gave JavaScript developers strong feelings about promises. They can almost certainly migrate to the native JavaScript promise now. Thank you literally everyone for joining me in this bet against the odds. Be excellent to each other.
npm warn deprecated
npm warn deprecated (For a CapTP with native promises, see @endo/eventual-send and @endo/captp)
npm warn deprecated fs-write-stream-atomic@1.0.10: This package is no longer supported.
npm warn deprecated sourcemap-codec@1.4.8: Please use @jridgewell/sourcemap-codec instead
npm warn deprecated sane@4.1.0: some dependency vulnerabilities fixed, support for node < 10 dropped, and newer ECMAScript syntax/features added
npm warn deprecated babel-eslint@10.1.0: babel-eslint is now @babel/eslint-parser. This package will no longer receive updates.
npm warn deprecated @hapi/address@2.1.4: Moved to 'npm install @sideway/address'
npm warn deprecated @humanwhocodes/object-schema@1.2.1: Use @eslint/object-schema instead
npm warn deprecated rollup-plugin-babel@4.4.0: This package has been deprecated and is no longer maintained. Please use @rollup/plugin-babel.
npm warn deprecated uuid@3.4.0: Please upgrade  to version 7 or higher.  Older versions may use Math.random() in certain circumstances, which is known to be problematic.  See https://v8.dev/blog/math-random for details.
npm warn deprecated @hapi/hoek@8.5.1: This version has been deprecated and is no longer supported or maintained
npm warn deprecated workbox-google-analytics@5.1.4: It is not compatible with newer versions of GA starting with v4, as long as you are using GAv3 it should be ok, but the package is not longer being maintained
npm warn deprecated @hapi/joi@15.1.1: Switch to 'npm install joi'
npm warn deprecated svgo@1.3.2: This SVGO version is no longer supported. Upgrade to v2.x.x.
npm warn deprecated @material-ui/styles@4.11.5: Material UI v4 doesn't receive active development since September 2021. See the guide https://mui.com/material-ui/migration/migration-v4/ to upgrade to v5.
npm warn deprecated eslint@7.32.0: This version is no longer supported. Please see https://eslint.org/version-support for other options.
npm warn deprecated core-js@2.6.12: core-js@<3.23.3 is no longer maintained and not recommended for usage due to the number of issues. Because of the V8 engine whims, feature detection in old core-js versions could cause a slowdown up to 100x even if nothing is polyfilled. Some versions have web compatibility issues. Please, upgrade your dependencies to the actual version of core-js.
npm warn deprecated @material-ui/core@4.12.4: Material UI v4 doesn't receive active development since September 2021. See the guide https://mui.com/material-ui/migration/migration-v4/ to upgrade to v5.

added 2331 packages, and audited 2540 packages in 2m

251 packages are looking for funding
  run `npm fund` for details

139 vulnerabilities (100 moderate, 32 high, 7 critical)

To address issues that do not require attention, run:
  npm audit fix

To address all issues (including breaking changes), run:
  npm audit fix --force

Run `npm audit` for details.
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Docker Build & Push)
[Pipeline] tool
[Pipeline] envVarsForTool
[Pipeline] withEnv
[Pipeline] {
[Pipeline] script
[Pipeline] {
[Pipeline] withDockerRegistry
$ /var/lib/jenkins/tools/org.jenkinsci.plugins.docker.commons.tools.DockerTool/docker/bin/docker login -u rafi345 -p ******** https://index.docker.io/v1/
Login Succeeded
[Pipeline] {
[Pipeline] sh
+ echo Building Docker image...
Building Docker image...
+ docker build --no-cache -t rafi345/bms:latest -f bookmyshow-app/Dockerfile bookmyshow-app
#0 building with "default" instance using docker driver

#1 [internal] load build definition from Dockerfile
#1 transferring dockerfile: 1.00kB done
#1 WARN: FromAsCasing: 'as' and 'FROM' keywords' casing do not match (line 30)
#1 DONE 0.0s

#2 [internal] load metadata for docker.io/library/node:18
#2 ...

#3 [auth] library/nginx:pull token for registry-1.docker.io
#3 DONE 0.0s

#4 [auth] library/node:pull token for registry-1.docker.io
#4 DONE 0.0s

#5 [internal] load metadata for docker.io/library/nginx:alpine
#5 ...

#2 [internal] load metadata for docker.io/library/node:18
#2 DONE 0.7s

#5 [internal] load metadata for docker.io/library/nginx:alpine
#5 DONE 0.7s

#6 [internal] load .dockerignore
#6 transferring context: 2B done
#6 DONE 0.0s

#7 [build 1/6] FROM docker.io/library/node:18@sha256:c6ae79e38498325db67193d391e6ec1d224d96c693a8a4d943498556716d3783
#7 DONE 0.0s

#8 [build 2/6] WORKDIR /app
#8 CACHED

#9 [stage-1 1/2] FROM docker.io/library/nginx:alpine@sha256:42a516af16b852e33b7682d5ef8acbd5d13fe08fecadc7ed98605ba5e3b26ab8
#9 CACHED

#10 [internal] load build context
#10 transferring context: 21.33MB 5.1s
#10 transferring context: 43.83MB 10.2s
#10 transferring context: 130.91MB 15.3s
#10 transferring context: 149.67MB 20.3s
#10 transferring context: 178.04MB 25.3s
#10 transferring context: 242.02MB 30.4s
#10 transferring context: 403.65MB 35.4s
#10 transferring context: 500.15MB 37.8s done
#10 DONE 38.1s

#11 [build 3/6] COPY package*.json ./
#11 DONE 1.0s

#12 [build 4/6] RUN npm install
#12 5.453 npm warn ERESOLVE overriding peer dependency
#12 5.454 npm warn While resolving: react-only-when@1.0.2
#12 5.454 npm warn Found: react@17.0.2
#12 5.454 npm warn node_modules/react
#12 5.454 npm warn   react@"^17.0.1" from the root project
#12 5.454 npm warn   58 more (@ant-design/icons, @ant-design/react-slick, ...)
#12 5.454 npm warn
#12 5.454 npm warn Could not resolve dependency:
#12 5.454 npm warn peer react@"^15.0.0 || ^16.0.0" from react-only-when@1.0.2
#12 5.454 npm warn node_modules/react-elastic-carousel/node_modules/react-only-when
#12 5.454 npm warn   react-only-when@"^1.0.2" from react-elastic-carousel@0.11.5
#12 5.454 npm warn   node_modules/react-elastic-carousel
#12 5.454 npm warn
#12 5.454 npm warn Conflicting peer dependency: react@16.14.0
#12 5.454 npm warn node_modules/react
#12 5.454 npm warn   peer react@"^15.0.0 || ^16.0.0" from react-only-when@1.0.2
#12 5.454 npm warn   node_modules/react-elastic-carousel/node_modules/react-only-when
#12 5.454 npm warn     react-only-when@"^1.0.2" from react-elastic-carousel@0.11.5
#12 5.454 npm warn     node_modules/react-elastic-carousel
#12 5.494 npm warn ERESOLVE overriding peer dependency
#12 5.494 npm warn While resolving: react-only-when@1.0.2
#12 5.494 npm warn Found: react-dom@17.0.2
#12 5.494 npm warn node_modules/react-dom
#12 5.494 npm warn   react-dom@"^17.0.1" from the root project
#12 5.494 npm warn   50 more (@ant-design/icons, @material-ui/core, ...)
#12 5.494 npm warn
#12 5.494 npm warn Could not resolve dependency:
#12 5.494 npm warn peer react-dom@"^15.0.0 || ^16.0.0" from react-only-when@1.0.2
#12 5.494 npm warn node_modules/react-elastic-carousel/node_modules/react-only-when
#12 5.494 npm warn   react-only-when@"^1.0.2" from react-elastic-carousel@0.11.5
#12 5.494 npm warn   node_modules/react-elastic-carousel
#12 5.494 npm warn
#12 5.494 npm warn Conflicting peer dependency: react-dom@16.14.0
#12 5.494 npm warn node_modules/react-dom
#12 5.494 npm warn   peer react-dom@"^15.0.0 || ^16.0.0" from react-only-when@1.0.2
#12 5.494 npm warn   node_modules/react-elastic-carousel/node_modules/react-only-when
#12 5.494 npm warn     react-only-when@"^1.0.2" from react-elastic-carousel@0.11.5
#12 5.494 npm warn     node_modules/react-elastic-carousel
#12 5.623 npm warn ERESOLVE overriding peer dependency
#12 5.623 npm warn While resolving: react-swipeable@5.5.1
#12 5.623 npm warn Found: react@17.0.2
#12 5.623 npm warn node_modules/react
#12 5.623 npm warn   react@"^17.0.1" from the root project
#12 5.623 npm warn   58 more (@ant-design/icons, @ant-design/react-slick, ...)
#12 5.623 npm warn
#12 5.623 npm warn Could not resolve dependency:
#12 5.623 npm warn peer react@"^16.0.0-0" from react-swipeable@5.5.1
#12 5.623 npm warn node_modules/react-elastic-carousel/node_modules/react-swipeable
#12 5.623 npm warn   react-swipeable@"^5.5.1" from react-elastic-carousel@0.11.5
#12 5.623 npm warn   node_modules/react-elastic-carousel
#12 5.623 npm warn
#12 5.623 npm warn Conflicting peer dependency: react@16.14.0
#12 5.623 npm warn node_modules/react
#12 5.623 npm warn   peer react@"^16.0.0-0" from react-swipeable@5.5.1
#12 5.623 npm warn   node_modules/react-elastic-carousel/node_modules/react-swipeable
#12 5.623 npm warn     react-swipeable@"^5.5.1" from react-elastic-carousel@0.11.5
#12 5.623 npm warn     node_modules/react-elastic-carousel
#12 14.53 npm warn deprecated w3c-hr-time@1.0.2: Use your platform's native performance.now() and performance.timeOrigin.
#12 14.53 npm warn deprecated urix@0.1.0: Please see https://github.com/lydell/urix#deprecated
#12 15.49 npm warn deprecated source-map-url@0.4.1: See https://github.com/lydell/source-map-url#deprecated
#12 15.60 npm warn deprecated stable@0.1.8: Modern JS already guarantees Array#sort() is a stable sort, so this library is deprecated. See the compatibility table on MDN: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort#browser_compatibility
#12 15.61 npm warn deprecated sourcemap-codec@1.4.8: Please use @jridgewell/sourcemap-codec instead
#12 15.73 npm warn deprecated source-map-resolve@0.5.3: See https://github.com/lydell/source-map-resolve#deprecated
#12 15.94 npm warn deprecated rollup-plugin-terser@5.3.1: This package has been deprecated and is no longer maintained. Please use @rollup/plugin-terser
#12 16.06 npm warn deprecated rimraf@3.0.2: Rimraf versions prior to v4 are no longer supported
#12 16.20 npm warn deprecated resolve-url@0.2.1: https://github.com/lydell/resolve-url#deprecated
#12 16.42 npm warn deprecated sane@4.1.0: some dependency vulnerabilities fixed, support for node < 10 dropped, and newer ECMAScript syntax/features added
#12 16.53 npm warn deprecated rollup-plugin-babel@4.4.0: This package has been deprecated and is no longer maintained. Please use @rollup/plugin-babel.
#12 16.70 npm warn deprecated querystring@0.2.1: The querystring API is considered Legacy. new code should use the URLSearchParams API instead.
#12 16.97 npm warn deprecated workbox-google-analytics@5.1.4: It is not compatible with newer versions of GA starting with v4, as long as you are using GAv3 it should be ok, but the package is not longer being maintained
#12 16.99 npm warn deprecated q@1.5.1: You or someone you depend on is using Q, the JavaScript Promise library that gave JavaScript developers strong feelings about promises. They can almost certainly migrate to the native JavaScript promise now. Thank you literally everyone for joining me in this bet against the odds. Be excellent to each other.
#12 16.99 npm warn deprecated
#12 16.99 npm warn deprecated (For a CapTP with native promises, see @endo/eventual-send and @endo/captp)
#12 18.30 npm warn deprecated move-concurrently@1.0.1: This package is no longer supported.
#12 18.49 npm warn deprecated lodash.template@4.5.0: This package is deprecated. Use https://socket.dev/npm/package/eta instead.
#12 19.47 npm warn deprecated inflight@1.0.6: This module is not supported, and leaks memory. Do not use it. Check out lru-cache if you want a good and tested way to coalesce async requests by a key value, which is much more comprehensive and powerful.
#12 19.98 npm warn deprecated glob@7.2.3: Glob versions prior to v9 are no longer supported
#12 20.28 npm warn deprecated flatten@1.0.3: flatten is deprecated in favor of utility frameworks such as lodash.
#12 20.37 npm warn deprecated figgy-pudding@3.5.2: This module is no longer supported.
#12 20.46 npm warn deprecated fs-write-stream-atomic@1.0.10: This package is no longer supported.
#12 21.14 npm warn deprecated domexception@2.0.1: Use your platform's native DOMException instead
#12 21.45 npm warn deprecated svgo@1.3.2: This SVGO version is no longer supported. Upgrade to v2.x.x.
#12 21.61 npm warn deprecated copy-concurrently@1.0.5: This package is no longer supported.
#12 22.86 npm warn deprecated abab@2.0.6: Use your platform's native atob() and btoa() methods instead
#12 23.01 npm warn deprecated babel-eslint@10.1.0: babel-eslint is now @babel/eslint-parser. This package will no longer receive updates.
#12 23.65 npm warn deprecated @npmcli/move-file@1.1.2: This functionality has been moved to @npmcli/fs
#12 23.80 npm warn deprecated @humanwhocodes/config-array@0.5.0: Use @eslint/config-array instead
#12 23.81 npm warn deprecated @hapi/topo@3.1.6: This version has been deprecated and is no longer supported or maintained
#12 23.81 npm warn deprecated @hapi/bourne@1.3.2: This version has been deprecated and is no longer supported or maintained
#12 24.31 npm warn deprecated @humanwhocodes/object-schema@1.2.1: Use @eslint/object-schema instead
#12 24.35 npm warn deprecated @hapi/address@2.1.4: Moved to 'npm install @sideway/address'
#12 24.53 npm warn deprecated @babel/plugin-proposal-private-methods@7.18.6: This proposal has been merged to the ECMAScript standard and thus this plugin is no longer maintained. Please use @babel/plugin-transform-private-methods instead.
#12 24.59 npm warn deprecated @babel/plugin-proposal-nullish-coalescing-operator@7.18.6: This proposal has been merged to the ECMAScript standard and thus this plugin is no longer maintained. Please use @babel/plugin-transform-nullish-coalescing-operator instead.
#12 24.59 npm warn deprecated @babel/plugin-proposal-optional-chaining@7.21.0: This proposal has been merged to the ECMAScript standard and thus this plugin is no longer maintained. Please use @babel/plugin-transform-optional-chaining instead.
#12 24.59 npm warn deprecated @babel/plugin-proposal-class-properties@7.18.6: This proposal has been merged to the ECMAScript standard and thus this plugin is no longer maintained. Please use @babel/plugin-transform-class-properties instead.
#12 24.59 npm warn deprecated @babel/plugin-proposal-numeric-separator@7.18.6: This proposal has been merged to the ECMAScript standard and thus this plugin is no longer maintained. Please use @babel/plugin-transform-numeric-separator instead.
#12 24.97 npm warn deprecated @hapi/hoek@8.5.1: This version has been deprecated and is no longer supported or maintained
#12 25.68 npm warn deprecated rimraf@2.7.1: Rimraf versions prior to v4 are no longer supported
#12 25.96 npm warn deprecated uuid@3.4.0: Please upgrade  to version 7 or higher.  Older versions may use Math.random() in certain circumstances, which is known to be problematic.  See https://v8.dev/blog/math-random for details.
#12 28.41 npm warn deprecated @hapi/joi@15.1.1: Switch to 'npm install joi'
#12 28.74 npm warn deprecated rimraf@2.7.1: Rimraf versions prior to v4 are no longer supported
#12 30.47 npm warn deprecated rimraf@2.7.1: Rimraf versions prior to v4 are no longer supported
#12 30.73 npm warn deprecated rimraf@2.7.1: Rimraf versions prior to v4 are no longer supported
#12 30.82 npm warn deprecated @babel/plugin-proposal-private-property-in-object@7.21.11: This proposal has been merged to the ECMAScript standard and thus this plugin is no longer maintained. Please use @babel/plugin-transform-private-property-in-object instead.
#12 32.88 npm warn deprecated @material-ui/styles@4.11.5: Material UI v4 doesn't receive active development since September 2021. See the guide https://mui.com/material-ui/migration/migration-v4/ to upgrade to v5.
#12 34.71 npm warn deprecated eslint@7.32.0: This version is no longer supported. Please see https://eslint.org/version-support for other options.
#12 39.70 npm warn deprecated core-js@2.6.12: core-js@<3.23.3 is no longer maintained and not recommended for usage due to the number of issues. Because of the V8 engine whims, feature detection in old core-js versions could cause a slowdown up to 100x even if nothing is polyfilled. Some versions have web compatibility issues. Please, upgrade your dependencies to the actual version of core-js.
#12 42.37 npm warn deprecated @material-ui/core@4.12.4: Material UI v4 doesn't receive active development since September 2021. See the guide https://mui.com/material-ui/migration/migration-v4/ to upgrade to v5.
#12 63.68 
#12 63.68 added 2329 packages, and audited 2538 packages in 1m
#12 63.68 
#12 63.68 252 packages are looking for funding
#12 63.68   run `npm fund` for details
#12 63.86 
#12 63.86 139 vulnerabilities (100 moderate, 32 high, 7 critical)
#12 63.86 
#12 63.86 To address issues that do not require attention, run:
#12 63.86   npm audit fix
#12 63.86 
#12 63.86 To address all issues (including breaking changes), run:
#12 63.86   npm audit fix --force
#12 63.86 
#12 63.86 Run `npm audit` for details.
#12 63.86 npm notice
#12 63.86 npm notice New major version of npm available! 10.8.2 -> 11.6.0
#12 63.86 npm notice Changelog: https://github.com/npm/cli/releases/tag/v11.6.0
#12 63.86 npm notice To update run: npm install -g npm@11.6.0
#12 63.86 npm notice
#12 DONE 65.0s

#13 [build 5/6] COPY . .
#13 DONE 99.3s

#14 [build 6/6] RUN npm run build
#14 0.618 
#14 0.618 > bookmyshow-app@0.1.0 build
#14 0.618 > react-scripts build
#14 0.618 
#14 3.333 Creating an optimized production build...
#14 79.20 Compiled with warnings.
#14 79.20 
#14 79.20 src/Components/BookTickets/Calendar.jsx
#14 79.20   Line 3:23:  'useSelector' is defined but never used  no-unused-vars
#14 79.20 
#14 79.20 src/Components/BookTickets/CinemasBody.jsx
#14 79.20   Line 1:17:   'useEffect' is defined but never used      no-unused-vars
#14 79.20   Line 16:11:  'data' is assigned a value but never used  no-unused-vars
#14 79.20 
#14 79.20 src/Components/BookTickets/Header.jsx
#14 79.20   Line 20:8:  React Hook useEffect has a missing dependency: 'dispatch'. Either include it or remove the dependency array  react-hooks/exhaustive-deps
#14 79.20 
#14 79.20 src/Components/PaymentsPage/SecondSection.jsx
#14 79.20   Line 46:110:  The href attribute requires a valid value to be accessible. Provide a valid, navigable address as the href value. If you cannot provide a valid href, but still need the element to resemble a link, use a button and change it with appropriate styles. Learn more: https://github.com/jsx-eslint/eslint-plugin-jsx-a11y/blob/HEAD/docs/rules/anchor-is-valid.md  jsx-a11y/anchor-is-valid
#14 79.20   Line 53:149:  The href attribute requires a valid value to be accessible. Provide a valid, navigable address as the href value. If you cannot provide a valid href, but still need the element to resemble a link, use a button and change it with appropriate styles. Learn more: https://github.com/jsx-eslint/eslint-plugin-jsx-a11y/blob/HEAD/docs/rules/anchor-is-valid.md  jsx-a11y/anchor-is-valid
#14 79.20 
#14 79.20 src/Components/Seating.jsx
#14 79.20   Line 1:17:   'useEffect' is defined but never used                                                                                                                                                                                                                                                              no-unused-vars
#14 79.20   Line 24:10:  'seatActive' is assigned a value but never used                                                                                                                                                                                                                                                    no-unused-vars
#14 79.20   Line 57:6:   React Hook React.useEffect has missing dependencies: 'ticketPrice1' and 'ticketPrice2'. Either include them or remove the dependency array. If 'setPrice' needs the current value of 'ticketPrice1', you can also switch to useReducer instead of useState and read 'ticketPrice1' in the reducer  react-hooks/exhaustive-deps
#14 79.20 
#14 79.20 src/Components/SummeryPage/Food.jsx
#14 79.20   Line 26:8:   React Hook React.useEffect has missing dependencies: 'dispatch', 'foods', and 'handleFilter'. Either include them or remove the dependency array                                                                                                                                                                                                                   react-hooks/exhaustive-deps
#14 79.20   Line 69:8:   React Hook React.useEffect has a missing dependency: 'dispatch'. Either include it or remove the dependency array                                                                                                                                                                                                                                                  react-hooks/exhaustive-deps
#14 79.20   Line 73:8:   React Hook React.useEffect has a missing dependency: 'dispatch'. Either include it or remove the dependency array                                                                                                                                                                                                                                                  react-hooks/exhaustive-deps
#14 79.20   Line 81:29:  The href attribute requires a valid value to be accessible. Provide a valid, navigable address as the href value. If you cannot provide a valid href, but still need the element to resemble a link, use a button and change it with appropriate styles. Learn more: https://github.com/jsx-eslint/eslint-plugin-jsx-a11y/blob/HEAD/docs/rules/anchor-is-valid.md  jsx-a11y/anchor-is-valid
#14 79.20 
#14 79.20 src/Pages/BookTicketsPage.jsx
#14 79.20   Line 17:11:  'movie_name' is assigned a value but never used                                                                         no-unused-vars
#14 79.20   Line 31:8:   React Hook useEffect has missing dependencies: 'dispatch' and 'id'. Either include them or remove the dependency array  react-hooks/exhaustive-deps
#14 79.20 
#14 79.20 src/Pages/HomePage.jsx
#14 79.20   Line 24:8:  React Hook useEffect has a missing dependency: 'dispatch'. Either include it or remove the dependency array  react-hooks/exhaustive-deps
#14 79.20 
#14 79.20 src/Pages/LoginPage.jsx
#14 79.20   Line 26:7:   'DialogTitle' is assigned a value but never used                                                                                                                                                                                                                                                                                                                   no-unused-vars
#14 79.20   Line 82:31:  The href attribute requires a valid value to be accessible. Provide a valid, navigable address as the href value. If you cannot provide a valid href, but still need the element to resemble a link, use a button and change it with appropriate styles. Learn more: https://github.com/jsx-eslint/eslint-plugin-jsx-a11y/blob/HEAD/docs/rules/anchor-is-valid.md  jsx-a11y/anchor-is-valid
#14 79.20   Line 82:90:  The href attribute requires a valid value to be accessible. Provide a valid, navigable address as the href value. If you cannot provide a valid href, but still need the element to resemble a link, use a button and change it with appropriate styles. Learn more: https://github.com/jsx-eslint/eslint-plugin-jsx-a11y/blob/HEAD/docs/rules/anchor-is-valid.md  jsx-a11y/anchor-is-valid
#14 79.20 
#14 79.20 src/Pages/PaymentsPage.jsx
#14 79.20   Line 5:8:   'ListItemText' is defined but never used           no-unused-vars
#14 79.20   Line 6:8:   'ListItem' is defined but never used               no-unused-vars
#14 79.20   Line 7:8:   'List' is defined but never used                   no-unused-vars
#14 79.20   Line 8:8:   'Divider' is defined but never used                no-unused-vars
#14 79.20   Line 11:8:  'IconButton' is defined but never used             no-unused-vars
#14 79.20   Line 14:8:  'ClearIcon' is defined but never used              no-unused-vars
#14 79.20   Line 15:8:  'ChevronLeftIcon' is defined but never used        no-unused-vars
#14 79.20   Line 17:8:  'Food' is defined but never used                   no-unused-vars
#14 79.20   Line 66:9:  'city' is assigned a value but never used          no-unused-vars
#14 79.20   Line 74:9:  'handleChange' is assigned a value but never used  no-unused-vars
#14 79.20 
#14 79.20 src/Pages/SeeAll.jsx
#14 79.20   Line 17:12:  'state' is assigned a value but never used                                                                                                                                                         no-unused-vars
#14 79.20   Line 17:19:  'setState' is assigned a value but never used                                                                                                                                                      no-unused-vars
#14 79.20   Line 22:8:   React Hook React.useEffect has a missing dependency: 'dispatch'. Either include it or remove the dependency array                                                                                  react-hooks/exhaustive-deps
#14 79.20   Line 57:8:   React Hook React.useEffect has missing dependencies: 'filterFormate.length', 'filterGenre.length', 'filterLanguage.length', and 'movies_data'. Either include them or remove the dependency array  react-hooks/exhaustive-deps
#14 79.20   Line 98:13:  'lan' is assigned a value but never used                                                                                                                                                           no-unused-vars
#14 79.20 
#14 79.20 src/Pages/SummeryPage.jsx
#14 79.20   Line 5:8:      'ListItemText' is defined but never used                                                                                                                                                                                                                                                                                                                           no-unused-vars
#14 79.20   Line 6:8:      'ListItem' is defined but never used                                                                                                                                                                                                                                                                                                                               no-unused-vars
#14 79.20   Line 7:8:      'List' is defined but never used                                                                                                                                                                                                                                                                                                                                   no-unused-vars
#14 79.20   Line 8:8:      'Divider' is defined but never used                                                                                                                                                                                                                                                                                                                                no-unused-vars
#14 79.20   Line 13:8:     'CloseIcon' is defined but never used                                                                                                                                                                                                                                                                                                                              no-unused-vars
#14 79.20   Line 46:10:    'open' is assigned a value but never used                                                                                                                                                                                                                                                                                                                          no-unused-vars
#14 79.20   Line 61:9:     'handleClickOpen' is assigned a value but never used                                                                                                                                                                                                                                                                                                               no-unused-vars
#14 79.20   Line 65:9:     'handleClose' is assigned a value but never used                                                                                                                                                                                                                                                                                                                   no-unused-vars
#14 79.20   Line 139:106:  The href attribute requires a valid value to be accessible. Provide a valid, navigable address as the href value. If you cannot provide a valid href, but still need the element to resemble a link, use a button and change it with appropriate styles. Learn more: https://github.com/jsx-eslint/eslint-plugin-jsx-a11y/blob/HEAD/docs/rules/anchor-is-valid.md  jsx-a11y/anchor-is-valid
#14 79.20   Line 149:145:  The href attribute requires a valid value to be accessible. Provide a valid, navigable address as the href value. If you cannot provide a valid href, but still need the element to resemble a link, use a button and change it with appropriate styles. Learn more: https://github.com/jsx-eslint/eslint-plugin-jsx-a11y/blob/HEAD/docs/rules/anchor-is-valid.md  jsx-a11y/anchor-is-valid
#14 79.20 
#14 79.20 src/Pages/moviePage/MoviePage.jsx
#14 79.20   Line 56:6:   React Hook React.useEffect has missing dependencies: 'dispatch' and 'id'. Either include them or remove the dependency array  react-hooks/exhaustive-deps
#14 79.20   Line 108:6:  React Hook React.useEffect has a missing dependency: 'dispatch'. Either include it or remove the dependency array             react-hooks/exhaustive-deps
#14 79.20 
#14 79.20 src/Redux/app/reducer.js
#14 79.20   Line 1:8:  'React' is defined but never used  no-unused-vars
#14 79.20 
#14 79.20 src/Redux/cinemas/cinemasReducer.js
#14 79.20   Line 1:8:  'React' is defined but never used  no-unused-vars
#14 79.20 
#14 79.20 src/Routes/Navbar.jsx
#14 79.20   Line 1:17:   'useState' is defined but never used                                                                               no-unused-vars
#14 79.20   Line 5:8:    'Button' is defined but never used                                                                                 no-unused-vars
#14 79.20   Line 7:8:    'DialogActions' is defined but never used                                                                          no-unused-vars
#14 79.20   Line 10:8:   'DialogTitle' is defined but never used                                                                            no-unused-vars
#14 79.20   Line 18:8:   'clsx' is defined but never used                                                                                   no-unused-vars
#14 79.20   Line 19:10:  'useReducer' is defined but never used                                                                             no-unused-vars
#14 79.20   Line 79:10:  'query' is assigned a value but never used                                                                         no-unused-vars
#14 79.20   Line 80:10:  'city' is assigned a value but never used                                                                          no-unused-vars
#14 79.20   Line 84:9:   'classes' is assigned a value but never used                                                                       no-unused-vars
#14 79.20   Line 105:6:  React Hook React.useEffect has a missing dependency: 'dispatch'. Either include it or remove the dependency array  react-hooks/exhaustive-deps
#14 79.20   Line 133:6:  React Hook React.useEffect has a missing dependency: 'dispatch'. Either include it or remove the dependency array  react-hooks/exhaustive-deps
#14 79.20 
#14 79.20 Search for the keywords to learn more about each warning.
#14 79.20 To ignore, add // eslint-disable-next-line to the line before.
#14 79.20 
#14 79.20 File sizes after gzip:
#14 79.20 
#14 79.27   219.18 KB  build/static/js/2.9c9285f6.chunk.js
#14 79.27   66.22 KB   build/static/css/2.cff87875.chunk.css
#14 79.27   31.54 KB   build/static/js/main.93d53605.chunk.js
#14 79.27   5.76 KB    build/static/css/main.376ba028.chunk.css
#14 79.27   1.62 KB    build/static/js/3.171f83f9.chunk.js
#14 79.27   1.17 KB    build/static/js/runtime-main.33e6ac0f.js
#14 79.27 
#14 79.27 The project was built assuming it is hosted at ./.
#14 79.27 You can control this with the homepage field in your package.json.
#14 79.27 
#14 79.27 The build folder is ready to be deployed.
#14 79.27 
#14 79.27 Find out more about deployment here:
#14 79.27 
#14 79.27   https://cra.link/deployment
#14 79.27 
#14 DONE 79.6s

#15 [stage-1 2/2] COPY --from=build /app/build /usr/share/nginx/html
#15 DONE 0.1s

#16 exporting to image
#16 exporting layers 0.1s done
#16 writing image sha256:58c0d3531c36d05366aa8c9665f7d91391e435624aa55b223e370a8a0dbf6cad done
#16 naming to docker.io/rafi345/bms:latest 0.0s done
#16 DONE 0.2s

 [33m1 warning found (use docker --debug to expand):
[0m - FromAsCasing: 'as' and 'FROM' keywords' casing do not match (line 30)
+ echo Pushing Docker image to registry...
Pushing Docker image to registry...
+ docker push rafi345/bms:latest
The push refers to repository [docker.io/rafi345/bms]
30aaa8a57e12: Preparing
f9985d3fc94d: Preparing
d208138be39d: Preparing
a2b76470e8f1: Preparing
917b2c97271e: Preparing
16ca725632e5: Preparing
7978a9c91f72: Preparing
b6ff0212304e: Preparing
418dccb7d85a: Preparing
16ca725632e5: Waiting
7978a9c91f72: Waiting
b6ff0212304e: Waiting
418dccb7d85a: Waiting
f9985d3fc94d: Layer already exists
917b2c97271e: Layer already exists
d208138be39d: Layer already exists
a2b76470e8f1: Layer already exists
16ca725632e5: Layer already exists
b6ff0212304e: Layer already exists
418dccb7d85a: Layer already exists
7978a9c91f72: Layer already exists
30aaa8a57e12: Pushed
latest: digest: sha256:0c43ffec26b7cbcdf29a18476cc80186044c300d0e15fefca823901bbe3bb369 size: 2200
[Pipeline] }
[Pipeline] // withDockerRegistry
[Pipeline] }
[Pipeline] // script
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Deploy to Container)
[Pipeline] tool
[Pipeline] envVarsForTool
[Pipeline] withEnv
[Pipeline] {
[Pipeline] sh
+ echo Stopping and removing old container...
Stopping and removing old container...
+ docker stop bms
bms
+ docker rm bms
bms
+ echo Running new container on port 3000...
Running new container on port 3000...
+ docker run -d --restart=always --name bms -p 3000:80 rafi345/bms:latest
00b79968639a1917f82e51ebfa8ac5fc0d1417a04a648f59c0b6417aa29ee408
+ echo Checking running containers...
Checking running containers...
+ docker ps -a
CONTAINER ID   IMAGE                     COMMAND                  CREATED                  STATUS                    PORTS                                         NAMES
00b79968639a   rafi345/bms:latest        "/docker-entrypoint.鈥?   Less than a second ago   Up Less than a second     0.0.0.0:3000->80/tcp, [::]:3000->80/tcp       bms
fa42585bfe6a   rafi345/bookmyshow:v19    "/docker-entrypoint.鈥?   23 hours ago             Exited (0) 23 hours ago                                                 bms-app
98537bf7e100   sonarqube:9.9-community   "/opt/sonarqube/dock鈥?   25 hours ago             Up 9 hours                0.0.0.0:9000->9000/tcp, [::]:9000->9000/tcp   sonarqube
+ echo Fetching logs...
Fetching logs...
+ sleep 5
+ docker logs bms
/docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
/docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
/docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
10-listen-on-ipv6-by-default.sh: info: Getting the checksum of /etc/nginx/conf.d/default.conf
10-listen-on-ipv6-by-default.sh: info: Enabled listen on IPv6 in /etc/nginx/conf.d/default.conf
/docker-entrypoint.sh: Sourcing /docker-entrypoint.d/15-local-resolvers.envsh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
/docker-entrypoint.sh: Configuration complete; ready for start up
2025/09/14 14:55:03 [notice] 1#1: using the "epoll" event method
2025/09/14 14:55:03 [notice] 1#1: nginx/1.29.1
2025/09/14 14:55:03 [notice] 1#1: built by gcc 14.2.0 (Alpine 14.2.0) 
2025/09/14 14:55:03 [notice] 1#1: OS: Linux 6.14.0-1012-aws
2025/09/14 14:55:03 [notice] 1#1: getrlimit(RLIMIT_NOFILE): 1048576:1048576
2025/09/14 14:55:03 [notice] 1#1: start worker processes
2025/09/14 14:55:03 [notice] 1#1: start worker process 30
2025/09/14 14:55:03 [notice] 1#1: start worker process 31
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // stage
[Pipeline] stage
[Pipeline] { (Declarative: Post Actions)
[Pipeline] script
[Pipeline] {
[Pipeline] emailext
Sending email to: rafishaik0066@gmail.com
[Pipeline] }
[Pipeline] // script
[Pipeline] }
[Pipeline] // stage
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // withEnv
[Pipeline] }
[Pipeline] // node
[Pipeline] End of Pipeline
Finished: SUCCESS
