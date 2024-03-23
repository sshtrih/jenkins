pipeline {
    agent {
        docker {
            image 'gcc:latest' // Используем контейнер с установленным компилятором C++
        }
    }
    stages {
        stage('Build') {
            steps {
                sh 'g++ -o my_binary main.cpp' // Компиляция исходного кода в бинарный файл
            }
            post {
                success {
                    archiveArtifacts artifacts: 'my_binary', onlyIfSuccessful: true // Архивирование бинарного файла
                }
            }
        }
    }
}
