# Username enumeration via response timing

## Objetivo

Explotar una vulnerabilidad de enumeración de usuarios para identificar un nombre de usuario válido y realizar un ataque de fuerza bruta sobre su contraseña para acceder a la cuenta.

## Solución

1. Intercepté la petición de login utilizando Burp Suite.\
   <img width="622" height="370" alt="image" src="https://github.com/user-attachments/assets/7b00cee9-3c7c-4bde-9d7b-46211f192902" />



2. Envié la petición al Intruder para fuzzear el nombre de usuario y a su vez el header `X-Forwarded-For:` para evitar el bloqueo de IP.\
   <img width="1247" height="373" alt="image" src="https://github.com/user-attachments/assets/77e37390-690d-4ddd-a455-cff90e4f7343" />



3. Utilicé una técnica de Pitchfork Attack y filtré el ataque según el tiempo que se tardó en procesar cada solicitud. Por esto es que anteriormente ingresé una contraseña larga.\
   <img width="1236" height="47" alt="image" src="https://github.com/user-attachments/assets/ff5fceb4-7ee6-4e20-882d-4e29bf3197a4" />



4. Identifiqué el nombre de usuario válido `announce` a partir del ataque anterior.



5. Utilicé fuerza bruta con una lista de contraseñas candidatas para encontrar la correspondiente con el nombre de usuario válido.\
   <img width="1247" height="63" alt="image" src="https://github.com/user-attachments/assets/c8c3b87c-9263-41f3-840a-ab4aefd1175d" />
   <img width="1230" height="47" alt="image" src="https://github.com/user-attachments/assets/d5ea0f1e-c81a-4070-9b98-f39c82d8ee48" />



6. Logré ingresar a la cuenta del usuario.\
   <img width="446" height="273" alt="image" src="https://github.com/user-attachments/assets/12221ec2-6767-48c6-b7b3-1149bf040205" />



## Herramientas utilizadas
- Burp Suite
- Navegador Web
