Algoritmo BeepTest

    Definir nombre como caracter
    Definir edad, participante, nivel, shuttle, totalParticipantes como entero 
    Definir V, VO2_Simple, VO2_leger, promSimple, promLeger Como Real

    participante <- 1
    promSimple <- 0
    PromLeger <- 0
    
    Escribir "¿Cuántos participantes hay?"
    Leer totalParticipantes

    Mientras participante <= totalParticipantes Hacer
        Escribir "Participante: ", participante

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
            Escribir "por favor ingrese un valor mayor o igual que 0"
            Leer shuttle
        FinMientras 

        V <- 8 + 0.5 * nivel

        VO2_Simple <- 3.46 * V + 12.2
        promSimple <- promSimple + VO2_Simple

        VO2_leger <- 31.025 + (3.238 * V) - (3.248 * edad) + (0.1536 * V * edad)
        promLeger <- promLeger + VO2_leger

        si VO2_Simple  >= 55 Entonces
		clasificacion = "Excelente"
        SiNo
            si VO2_Simple >=45 Entonces
                clasificacion = "Buena"
            SiNo
                si VO2_Simple >=35 Entonces
                    clasificacion = "Promedio"
                SiNo
                    si  VO2_Simple <35 Entonces
                        clasificacion = "Baja"
                    FinSi
                FinSi
            FinSi
        FinSi
      
        Escribir "------------------------------"
        Escribir "participante ", participante, ": ", nombre
        Escribir "Edad: ", edad, " años"
        Escribir "Nivel alcanzado: ", nivel
        Escribir "Shuttle: ", shuttle
        Escribir "Velocidad final: ", V, " Km/h"
        Escribir "VO2_Máx_Simple: ",  VO2_Simple
        Escribir "VO2_Máx_leger: ", VO2_leger  
        Escribir "Clasificacion: ", clasificacion
        Escribir "------------------------------"

        participante <- participante + 1

    FinMientras

    Escribir "Promedio grupal VO2 simple: ", (promSimple / totalParticipantes)
    Escribir "Promedio grupal VO2 Léger: ", (PromLeger / totalParticipantes)


FinAlgoritmo


