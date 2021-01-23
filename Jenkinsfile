pipeline {
  agent { node { label 'master' } } 
  stages{
    stage('Clone the repo'){
	  steps {
	  git changelog: false, url: 'https://github.com/mohansgithub/mohan-web-app.git'
	  }
    }
	stage('Build'){
	  steps {
	  bat 'mvn clean package'
	  }
	}
	stage('unit tests'){
	  steps {
	  echo "step3"
	  }
    }
	stage('package upload'){
	  steps {
	  echo "step4"
	  }
	}
    stage('package download'){
	  steps {
	  echo "step4"
	  }
	}
	stage('deploy package'){
	  steps {
	  deploy adapters: [tomcat8(credentialsId: '82f076e6-588d-4290-8b7e-27f8265ff1f9', path: '', url: 'http://localhost:7080')], contextPath: '/simple-web-app', war: '**/*.war'
	  }
	}
  }
}