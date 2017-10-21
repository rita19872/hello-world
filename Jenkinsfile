node {
   def mvnHome
   stage('checkout') {
      checkout scm
      mvnHome = tool name: 'M2', type: 'maven'
      env.JAVA_HOME = tool 'JDK1.8'
   }
   stage('Build') {
     if (isUnix()) {
         sh "'${mvnHome}/bin/mvn' clean install"
      } else {
           bat(/"${mvnHome}\bin\mvn" clean install/)
      }
   }

}
