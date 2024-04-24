contenido = "Informacion de las operaciones aritmeticas:\n" 
pipeline {
    agent any
    
    options {
        timeout(time:5, unit: 'MINUTES')
    }
    
    environment {
         RUTA_ABSOLUTA = "C:\\"
    }

    stages {
        stage('Stage 1: Operaciones aritmeticas') {
            steps {
                script {
                    def numero1 = 100
                    def numero2 = 50
                    
                    def suma = numero1 + numero2
                    def resta = numero1 - numero2
                    def multiplicacion = numero1 * numero2
                    def division = numero1 / numero2

                    contenido += "Suma: ${suma}\n"
                    contenido += "Resta: ${resta}\n"
                    contenido += "Multiplicacion: ${multiplicacion}\n"
                    contenido += "Division: ${division}\n"
                    
                    println contenido
                }
            }
        }
        
        stage('Stage 2: Ejecutar comando bat') {
            steps {
                bat 'ipconfig /flushdns'
            }
        }
        
        stage('Stage 3: Generar archivo txt') {
            steps {
                script {
                    path = RUTA_ABSOLUTA + "informacion_operaciones.txt"
                    writeFile(file: path , text: contenido)
                    
                    println "Se ha generado el archivo informacion_operaciones.txt"
                }
            }
        }
    }
    
    post {
        always {
            echo "Mostrar siempre desde post"
        }
    }
}

