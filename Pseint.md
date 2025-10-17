Algoritmo BeepTest

    Definir nombre, clasificacion como cadena
    Definir edad, participante, nivel, shuttle, totalParticipantes como entero 
    Definir V, VO2_Simple, VO2_leger, promSimple, promLeger Como Real

    promSimple <- 0
    promLeger <- 0
    
    Escribir "¿Cuántos participantes hay?"
    Leer totalParticipantes

    Mientras totalParticipantes < 1 Hacer
        Escribir "Ingrese un número valido mayor o igual que 1"
        Leer totalParticipantes
    FinMientras

    Para participante <- 1 Hasta totalParticipantes Hacer
        Escribir "Participante ", participante, ": "

        Escribir "¿Cuál es su nombre?"
        Leer nombre 

        Escribir "¿Cuál es la edad?" 
        Leer edad 
        Mientras edad <= 0 Hacer 
            Escribir "Por favor ingrese una edad mayor a 0"
            Leer edad
        FinMientras

        Escribir "¿Cuál fue el nivel alcanzado?"
        Leer nivel 
        Mientras nivel < 1 Hacer 
            Escribir "Por favor ingrese un valor mayor o igual que 1"
            Leer nivel
        FinMientras

        Escribir "¿Cuál es el shuttle?" 
        Leer shuttle
        Mientras shuttle < 0 Hacer
            Escribir "por favor ingrese un valor mayor o igual que 0"uien creo github
            Leer shuttle
        FinMientras 

        V <- 8 + 0.5 * nivel
            /// El test empieza en 8km/h y aumenta 0.5 por cada nivel

        VO2_Simple <- 3.46 * V + 12.2
        promSimple <- promSimple + VO2_Simple
            /// 3.46: aumento del VO₂ por cada 1 km/h
            /// 12.2: valor base del VO₂

        VO2_leger <- 31.025 + (3.238 * V) - (3.248 * edad) + (0.1536 * V * edad)
        promLeger <- promLeger + VO2_leger
            ///31.025: base del modelo
            ///3.238: VO₂ sube con velocidad
            //-3.248: VO₂ baja con la edad
            //0.1536: efecto combinado de edad y velocidad
            
        si VO2_Simple  >= 55 Entonces
		clasificacion <- "Excelente"
        SiNo
            si VO2_Simple >= 45 Entonces
                clasificacion <- "Buena"
            SiNo
                si VO2_Simple >= 35 Entonces
                    clasificacion <- "Promedio"
                SiNo
                    clasificacion <- "Baja"                   
                FinSi
            FinSi
        FinSi
      
        Escribir "                              "
        Escribir "=============================="
        Escribir "participante ", participante, ": ", nombre
        Escribir "Edad: ", edad, " años"
        Escribir "Nivel alcanzado: ", nivel
        Escribir "Shuttle: ", shuttle
        Escribir "Velocidad final: ", V, " Km/h"
        Escribir "VO2_Máx_Simple: ",  VO2_Simple
        Escribir "VO2_Máx_leger: ", VO2_leger  
        Escribir "Clasificación: ", clasificacion
        Escribir "=============================="
        Escribir "                              "

        
    FinPara

    Escribir "Promedio grupal VO2 simple: ", (promSimple / totalParticipantes)
    Escribir "Promedio grupal VO2 Léger: ", (promLeger / totalParticipantes)


FinAlgoritmo


