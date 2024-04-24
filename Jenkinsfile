pipeline {
    agent any
    
    options {
        timeout(time:5, unit: 'MINUTES')
    }
    
    environment {
         RUTA_ABSOLUTA = "C:\\"
    }
    
   variables {   
    contenido = "Información de las operaciones aritméticas:\n"     
   }
    stages {
        stage('Stage 1: Operaciones aritméticas') {
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
                    contenido += "Multiplicación: ${multiplicacion}\n"
                    contenido += "División: ${division}\n"
                    
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
                    
                    writeFile(file: informacion_operaciones.txt, text: contenido)
                    
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

