# Username enumeration via subtly different responses

## Objetivo

Explotar una vulnerabilidad de enumeración de usuarios para identificar un nombre de usuario válido y realizar un ataque de fuerza bruta sobre su contraseña para acceder a la cuenta.

## Solución

1. Intercepté la petición de login utilizando Burp Suite.\
   <img width="616" height="375" alt="image" src="https://github.com/user-attachments/assets/586c0020-2488-4bf8-8600-5b267102ded0" />


   
2. Envié la petición al Intruder para fuzzear con una lista de posibles nombres de usuario.\
   <img width="607" height="352" alt="image" src="https://github.com/user-attachments/assets/b1fd4e71-27f8-42ba-a53e-5ab1c1ef66ed" />



3. Utilicé una técnica de Sniper Attack y filtré con negative search para excluir las respuestas que entregaban el error comun.\
   <img width="625" height="197" alt="image" src="https://github.com/user-attachments/assets/72bab092-b675-4f9a-ab61-a1110335f69b" />



4. Identifiqué el nombre de usuario válido `adkit` a partir del ataque anterior.\
   <img width="1272" height="45" alt="image" src="https://github.com/user-attachments/assets/3302e535-5419-41d7-b69d-729056d03f67" />



5. Utilicé fuerza bruta con una lista de contraseñas candidatas para encontrar la correspondiente con el nombre de usuario válido.\
   <img width="237" height="20" alt="image" src="https://github.com/user-attachments/assets/0343dbad-6a3b-41a0-ba49-a51d8bf551b9" />\
   <img width="1285" height="37" alt="image" src="https://github.com/user-attachments/assets/a8c842a6-44a9-4161-9a1c-a2b7f7ec6e9d" />



6. Logré ingresar a la cuenta del usuario.\
   <img width="462" height="277" alt="image" src="https://github.com/user-attachments/assets/9e440a8e-8e9a-40ab-85a3-40a2779a5ed4" />




## Herramientas utilizadas
- Burp Suite
- Navegador Web
