# Username enumeration via different responses

## Objetivo

Explotar una vulnerabilidad de enumeración de usuarios para identificar un nombre de usuario válido y realizar un ataque de fuerza bruta sobre su contraseña para acceder a la cuenta.

## Solución

1. Intercepté la petición de login utilizando Burp Suite.\
   <img width="616" height="367" alt="image" src="https://github.com/user-attachments/assets/9597b5e8-32b3-4022-88e5-99ae133e319f" />



2. Envié la petición al Intruder para fuzzear con una lista de posibles nombres de usuario.\
   <img width="611" height="362" alt="image" src="https://github.com/user-attachments/assets/5e575666-1797-43b1-8b2f-2fb581acbe08" />



3. Utilicé una técnica de Sniper Attack y detecté un nombre de usuario que entregaba un error diferente a los demás.\
   <img width="1280" height="141" alt="image" src="https://github.com/user-attachments/assets/418e791b-cb26-49c8-8cf0-5b137bc2f4b8" />


   
4. Identifiqué el nombre de usuario válido 'apps' a partir del ataque anterior.\


5. Utilicé fuerza bruta con una lista de contraseñas candidatas para encontrar la correspondiente con el nombre de usuario válido.\
   <img width="261" height="25" alt="image" src="https://github.com/user-attachments/assets/f3479dc8-8087-4f92-9dff-3a83e2de2698" />\
   <img width="607" height="46" alt="image" src="https://github.com/user-attachments/assets/9c792088-7368-46bb-a7cd-b7beaf26a988" />

6. Logré ingresar a la cuenta del usuario.\
   <img width="1165" height="192" alt="image" src="https://github.com/user-attachments/assets/61d8a816-4036-41c2-abcc-050dbe069e68" />




## Herramientas utilizadas
- Burp Suite
- Navegador Web
