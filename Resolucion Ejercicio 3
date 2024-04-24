/*
Ejercicio 3: 
En tu repositorio de Github debes tener al menos 3 ramas: master, desarrollo y UAT. 
Las cuales deben ser iguales. Dentro de la rama de desarrollo se debe generar un Jenkinsfile que haga lo siguiente:
Stage 1: 
- Realizar operaciones aritmeticas generales con dos numeros agregados e informar por
consola los valores
Stage 2: 
- Realizar un comando de tipo bat ipconfig /flushdns
Stage 3: 
- Generar un archivo de TXT con la información del Stage 1 e informar por consola
que se genero el fichero
Tener en cuenta que el codigo debe declarar las siguientes secciones:
- options
- environment 
- seccion de post

Entregables:
- Link del repositorio de Github
- Captura de la consola de Jenkins

*/
                    def numero1 = 100
                    def numero2 = 100
                    def suma = numero1+numero2
                    def resta = numero1-numero2
                    def mult = numero1*numero2
                    def div = numero1 / numero2
                    def string = "Informo por consola los valores, suma: " + suma + " , resta: " + resta + " , multiplicacion:" +mult + " y la division es: " + div
pipeline
{
    agent any
    options
    {
        timeout(time:5, unit: "MINUTES")
    }
    
    stages
    {
        stage("Stage 1: Calculos Aritmeticos")
        {
            steps
            {
                script
                {
                    println string
                }
            }
        }
        
        stage("Comandos de tipo BAT")
        {
            steps
            {
                bat 'ipconfig /flushdns'
            }
        }
        
        stage("Genero fichero")
        {
            steps
            {
                script
                {
                    writeFile(file: "salida_fichero.txt", text:string)
                    echo 'Se genero el fichero de salida.'
                }
            }
        }
    }

post
{
    always
    {
        echo 'se ejecuto el pipeline'
    }
    
    success
    {
        echo 'Se ejecuto correctamente'
    }
    
    failure
    {
        echo "Fallo el pipeline, vea el log de la consola. "
    }
    
}

}
