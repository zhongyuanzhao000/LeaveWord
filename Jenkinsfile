pipeline {
    agent any
    stages {
	
		stage('Clone') {
			steps {
				echo "1.Clone Stage"
				git url: "https://github.com/zhongyuanzhao000/LeaveWord.git"
			}
		}
		stage('Package & skip Test') {
			steps {
				echo "2.Package Stage"
				sh 'mvn clean package -DskipTests'
			}
		}
		stage('Build') {
			steps {
				echo "3.Build Docker Image Stage"
				sh "sudo /usr/local/bin/docker-compose build"
			}
		}
		stage('Deploy') {
			steps {
			echo "4. Deploy Stage"
			sh "sudo /usr/local/bin/docker-compose up"
			}
		}
	
	}

}
