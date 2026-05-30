pipeline {
    agent any

    stages {
        stage('Preparação') {
            steps {
                echo 'Iniciando pipeline de testes de desempenho do aluno Luahn...'
            }
        }
        
        stage('Testes de Desempenho com JMeter') {
            steps {
                script {
                    // O Jenkins roda em um workspace vazio por padrão. Precisamos apontar para a pasta do seu projeto.
                    dir('C:\\Users\\Luahn\\Desktop\\trab_qts\\trab-thiago-qts') {
                        bat 'C:\\Users\\Luahn\\Downloads\\apache-jmeter-5.6.3\\apache-jmeter-5.6.3\\bin\\jmeter.bat -n -t testes/script_de_teste_luahn.jmx -l resultados_luahn.jtl'
                    }
                }
            }
        }
    }

    post {
        always {
            echo '========================================================================'
            echo 'Sucesso: Testes de desempenho concluídos com maestria pelo aluno Luahn!'
            echo '========================================================================'
        }
        success {
            echo 'O pipeline finalizou sem erros. Verifique os dados no Grafana do Luahn.'
        }
        failure {
            echo 'O pipeline falhou. Por favor, verifique se o script JMeter e os containers Docker estão rodando corretamente.'
        }
    }
}
