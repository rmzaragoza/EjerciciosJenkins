pipeline {
    agent any
    
    options {
        timeout(time:5, unit: 'MINUTES')
    }
    
    environment {
         RUTA_ABSOLUTA = "C:\\"
    }
    
    def suma 
    def resta
    def multiplicacion
    def division
        
    stages {
        stage('Stage 1: Operaciones aritméticas') {
            steps {
                script {
                    def numero1 = 100
                    def numero2 = 50
                    
                    suma = numero1 + numero2
                    resta = numero1 - numero2
                    multiplicacion = numero1 * numero2
                    division = numero1 / numero2
                    
                    println "Suma: ${suma}"
                    println "Resta: ${resta}"
                    println "Multiplicación: ${multiplicacion}"
                    println "División: ${division}"
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
                    def contenido = "Información de las operaciones aritméticas:\n"
                    contenido += "Suma: ${suma}\n"
                    contenido += "Resta: ${resta}\n"
                    contenido += "Multiplicación: ${multiplicacion}\n"
                    contenido += "División: ${division}\n"
                    
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

