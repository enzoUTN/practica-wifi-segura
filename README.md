# Informe de Auditoría de Red Wi-Fi Insegura

Para este informe vamos a utilizar una máquina virtual, que tiene como sistema operativo Kali Linux. En la máquina virtual, vamos a utilizar el navegador Firefox. El objetivo principal de este informe es documentar, analizar y auditar el tráfico que podría haber en una red wifi pública, identificando los posibles riesgos, las vulnerabilidades y proponer soluciones. 

Para lograr este objetivo vamos a ingresar y analizar un sitio web (http://neverssl.com), en donde determinaremos el protocolo que utiliza y la información que puede quedar expuesta. Vamos a explicar la importancia de usar una VPN en redes públicas y vamos a adjuntar toda evidencia por medio de capturas de pantalla. 

## Parte 1 – Exploración

Iniciamos la máquina virtual, abrimos el navegador Firefox e ingresamos a la siguiente página http://neverssl.com.

<img width="1408" height="881" alt="Captura de pantalla 2026-09-28 a la(s) 12 53 45 a  m" src="https://github.com/user-attachments/assets/60493a72-b126-4a56-aa07-6b2b53507a4b" />

Como podemos observar, cuando ingresamos a la página nos aparece en la barra donde esta el URL una advertencia: NOT SECURE. Esto ya nos da una pista de qué tipo de protocolo está utilizando la página. Pero para poder confirmar su protocolo y otros datos vamos a ingresar al modo inspeccion del navegador.  

Click derecho -> Inspect (Q) -> Vamos a la sección Network -> Recargamos la página. Esto nos mostrará algunos datos interesantes para el análisis de protocolo. Al recargar la pagina seleccionamos la primer solicitud realizada. 

<img width="1408" height="881" alt="Captura de pantalla 2026-09-28 a la(s) 1 03 17 a  m" src="https://github.com/user-attachments/assets/f01e6f46-5d0f-4315-ae0c-26f6d66b7744" />

En la anterior imagen podemos observar un apartado en la izquierda inferior derecha (marcado por rojo). En esa parte de la pantalla observamos distintos datos:

<img width="587" height="733" alt="Captura de pantalla 2026-09-28 a la(s) 1 21 13 a  m" src="https://github.com/user-attachments/assets/de107bcc-f340-4e63-8e69-0a32bed3ef09" />

- URL Solicitada: GET http://beautifulwonderfuloldeclipse.neverssl.com/online/
- Método HTTP: HTTP/1.1
- Host: beautifulwonderfuloldeclipse.neverssl.com
- Protocolo utilizado: HTTP
- Headers enviados:
  - GET /online/ HTTP/1.1
  - Host: beautifulwonderfuloldeclipse.neverssl.com
  - User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:140.0) Gecko/20100101 Firefox/140.0
  - Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
  - Accept-Language: en-US,en;q=0.5
  - Accept-Encoding: gzip, deflate
  - Referer: http://neverssl.com/
  - DNT: 1
  - Sec-GPC: 1
  - Connection: keep-alive
  - Upgrade-Insecure-Requests: 1
  - Priority: u=0, i




