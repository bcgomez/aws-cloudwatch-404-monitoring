# 🧠 AWS CloudWatch 404 Monitoring

Monitoreo de errores HTTP 404 en un servidor web usando AWS CloudWatch, métricas, alarmas y SNS.

---

![AWS](https://img.shields.io/badge/AWS-CloudWatch-orange)
![Monitoring](https://img.shields.io/badge/Monitoring-Active-brightgreen)
![Status](https://img.shields.io/badge/Status-Completed-success)
![Type](https://img.shields.io/badge/Project-DevOps-blue)

---

## 📌 1. Introducción

Este laboratorio implementa una solución de monitoreo para detectar errores HTTP 404 en un servidor web desplegado en Amazon EC2, utilizando servicios de AWS como CloudWatch Logs, Metric Filters, CloudWatch Alarms y Amazon SNS.

El objetivo es transformar eventos de logs en métricas accionables y generar alertas automáticas ante comportamientos anómalos.

---

## ⚠️ 2. Problemática

Las aplicaciones web pueden generar errores (como HTTP 404) que afectan la experiencia del usuario. Sin un sistema de monitoreo adecuado:

- ❌ No se detectan los errores a tiempo  
- ❌ No existen alertas automáticas  
- ❌ Se depende de reportes manuales de los usuarios  

Esto genera una respuesta reactiva en lugar de proactiva.

---

## 💡 3. Solución

Se implementa una arquitectura de monitoreo basada en:

- 📊 **CloudWatch Logs** → Captura y almacenamiento de logs  
- 🔍 **Metric Filters** → Detección de patrones (errores 404)  
- 🚨 **CloudWatch Alarms** → Generación de alertas  
- 📧 **Amazon SNS** → Notificación automática por correo  

---

## ⚙️ 4. Implementación

---

### 🔹 4.1 Verificación del servidor Apache

Se valida que el servidor web Apache esté correctamente desplegado en la instancia EC2.

![Apache](images/Picture1.png)  
*Figura 1. Página de prueba del servidor Apache funcionando correctamente.*

---

### 🔹 4.2 Generación de error HTTP 404

Se accede a una ruta inexistente para generar un error controlado.

![Error 404](images/Picture2.png)  
*Figura 2. Generación de error HTTP 404 al acceder a una ruta inexistente.*

---

### 🔹 4.3 Configuración de logs en CloudWatch

Se configuran los grupos de logs para almacenar los eventos del servidor web.

![Log groups](images/Picture3.png)  
*Figura 3. Grupos de logs creados para almacenar eventos del servidor.*

---

### 🔹 4.4 Visualización de eventos

Se inspeccionan los logs generados por las solicitudes HTTP.

![Log events](images/Picture4.png)  
*Figura 4. Visualización de eventos HTTP en CloudWatch Logs.*

---

### 🔹 4.5 Creación del Metric Filter

Se define un filtro para detectar automáticamente errores 404 en los logs.

![Metric filter](images/Picture5.png)  
*Figura 5. Definición del filtro para detectar errores 404 en logs.*

---

### 🔹 4.6 Validación del filtro

Se prueba el filtro para confirmar que detecta correctamente los eventos.

![Test filter](images/Picture6.png)  
*Figura 6. Validación del filtro mostrando coincidencias con errores 404.*

---

### 🔹 4.7 Configuración de la métrica

Se crea una métrica personalizada basada en los errores detectados.

![Metric config](images/Picture7.png)  
*Figura 7. Configuración de la métrica basada en errores 404.*

---

### 🔹 4.8 Configuración de notificaciones (SNS)

Se configura Amazon SNS para enviar alertas por correo electrónico.

![SNS](images/Picture8.png)  
*Figura 8. Configuración del envío de notificaciones mediante SNS.*

---

### 🔹 4.9 Detalles de la alarma

Se define el nombre y descripción de la alarma.

![Alarm details](images/Picture9.png)  
*Figura 9. Definición del nombre y descripción de la alarma.*

---

### 🔹 4.10 Creación de la alarma

Se crea la alarma en CloudWatch basada en la métrica generada.

![Alarm created](images/Picture10.png)  
*Figura 10. Confirmación de creación de la alarma en CloudWatch.*

---

### 🔹 4.11 Activación de la alarma

Se generan múltiples errores para activar la alarma y validar el sistema.

![Alarm triggered](images/Picture11.png)  
*Figura 11. Activación de la alarma tras generar múltiples errores 404.*

---

## ✅ 5. Validación

Se verificó el correcto funcionamiento del sistema mediante:

- ✔ Generación de errores HTTP 404  
- ✔ Registro en CloudWatch Logs  
- ✔ Conversión de eventos a métricas  
- ✔ Activación automática de alarmas  
- ✔ Recepción de notificaciones vía SNS  

---

## 📊 6. Conclusión

Se implementó exitosamente un sistema de monitoreo proactivo capaz de detectar errores en tiempo real y generar alertas automáticas.

Esta solución mejora significativamente la observabilidad del sistema y permite una respuesta rápida ante fallos en la aplicación.

---

## 🧠 7. Valor Profesional

Este proyecto demuestra habilidades en:

- ☁️ AWS CloudWatch (Logs, Metrics, Alarms)  
- 🔍 Observabilidad y monitoreo  
- 🚨 Automatización de alertas  
- 🧩 Análisis de logs  

---

## 👩‍💻 Autor

**Barbara Catalina Gómez Pérez**  
Proyecto de formación en Cloud Computing y DevOps 🚀
