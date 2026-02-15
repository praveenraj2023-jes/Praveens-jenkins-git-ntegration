1  pipeline {
2      agent any
3  
4      stages {
5          stage('Clean Workspace') {
6              steps {
7                  echo 'Cleaning workspace before build...'
8                  cleanWs()
9              }
10         }
11         stage('Checkout') {
12             steps {
13                 echo 'Checking out code from GitHub...'
14             }
15         }
16         stage('Build') {
17             steps {
18                 echo 'Building the project...'
19                 bat 'echo Build completed successfully.'
20             }
21         }
22         stage('Test') {
23             steps {
24                 echo 'Running tests...'
25                 bat 'echo All tests passed.'
26             }
27         }
28     }
29 
30     post {
31         always {
32             echo 'Pipeline finished. Cleaning up...'
33         }
34         success {
35             echo '🎉 SUCCESS: The pipeline completed successfully!'
36         }
37         failure {
38             echo '❌ FAILURE: The pipeline failed. Check the logs for details.'
39         }
40         unstable {
41             echo '⚠️ UNSTABLE: The pipeline is unstable (e.g., test failures).'
42         }
43         changed {
44             echo '📊 Status changed from the previous build.'
45         }
46     }
47 }