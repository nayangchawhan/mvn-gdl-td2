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
        sh 'mvn clean package'
      }
    }

    stage('build'){
      steps{
        sh 'mvn compile'
      }
    }

    stage('test'){
      steps{
        sh 'mvn test'
      }
    }

    stage('run application'){
      steps{
        sh 'java -jar target/myapp01-test-1.0-SNAPSHOT.jar'
      }
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
