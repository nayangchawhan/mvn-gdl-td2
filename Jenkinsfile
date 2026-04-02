pipeline{
  agent any
  
  tools{
    maven 'Maven'
    jdk 'jdk'
  }

  stages{
    stage('checkout'){
      steps{
        git branch:'master',url:'https://github.com/nayangchawhan/mvn-gdl-td2'
      }
    }
    
    stage('package'){
      steps{
        dir('app'){
        sh 'mvn clean package'
      }}
    }

    stage('build'){
      steps{
        dir('app'){
        sh 'mvn compile'
      }}
    }

    stage('test'){
      steps{
        dir('app'){
        sh 'mvn test'
      }}
    }

    stage('run application'){
      steps{
        dir('app'){
        sh 'java -jar target/myapp01-test-1.0-SNAPSHOT.jar'
      }}
    }
  }

  post{
    success{
      echo 'Build success'
    }

    failure{
      echo 'build failed'
    }
  }
  
}
