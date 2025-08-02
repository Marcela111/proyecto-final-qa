



Suite de Automatización Funcional
Situación Inicial y Objetivo del Proyecto
Situación Inicial
El área de Calidad y Testing de nuestra empresa de desarrollo de software identificó que los defectos en el proceso de registro e inicio de sesión se descubrían tardíamente, lo que generaba altos costos y retrasos. Para mitigar este riesgo, se solicitó la creación de una suite de pruebas automatizadas con Selenium.

Nuestro Objetivo
El objetivo de este proyecto fue desarrollar y ejecutar una suite de automatización funcional para:

Validar los flujos críticos de registro y login.

Generar evidencias de ejecución (capturas de pantalla, logs, reportes).

Establecer una base de pruebas de regresión que pueda ser extendida a futuros módulos de la aplicación.

Arquitectura de Pruebas (Patrón POM)
Para construir una suite de pruebas robusta y fácil de mantener, se utilizó el patrón de diseño Page Object Model (POM). Este patrón nos permitió separar la lógica de negocio de los tests de la interacción con los elementos de la interfaz de usuario.

La estructura del proyecto sigue una organización clara:

tu-proyecto-de-automatizacion/
├── src/main/java/
│   └── com/tuempresa/
│       ├── pages/               # Clases "Page Object" que contienen localizadores y métodos.
│       │   ├── LoginPage.java
│       │   ├── RegistroPage.java
│       │   └── ReservaPage.java
│       └── utils/               # Clases de utilidades y configuración.
│           ├── BaseTest.java
│           └── ScreenshotListener.java
├── src/test/java/
│   └── com/tuempresa/
│       └── tests/               # Clases de prueba con los escenarios de testing.
│           ├── LoginTest.java
│           └── RegistroTest.java
├── target/                      # Directorio generado por Maven con reportes y evidencias.
├── pom.xml                      # Archivo de configuración de Maven.
└── testng.xml                   # Archivo de configuración para la suite de TestNG.
Tecnologías y Dependencias
Lenguaje: Java

Automatización: Selenium WebDriver

Framework de Pruebas: TestNG

Gestión de Dependencias: Maven

Gestión de Drivers: WebDriverManager

Entorno de Desarrollo: Visual Studio Code

Escenarios de Prueba Automatizados
La suite de automatización cubre los siguientes escenarios críticos de la aplicación:

Login
Login Exitoso: Se verifica el acceso con credenciales válidas.

Login Fallido: Se valida que el sistema rechace el acceso con credenciales inválidas.

Login Fallido con Múltiples Intentos: Se simulan varios intentos de login fallidos para validar que el sistema no permita el acceso.

Registro de Usuario
Registro Exitoso: Se valida que el registro con datos válidos cree un nuevo usuario.

Registro Fallido: Se valida que el formulario de registro muestre mensajes de error con datos inválidos, como contraseñas que no coinciden.

Pruebas con Múltiples Datos: Se utiliza un DataProvider para ejecutar 6 combinaciones de datos diferentes en la prueba de registro, aumentando la cobertura de manera eficiente.

Lecciones Aprendidas y Aspectos Clave
Este proyecto fue fundamental para dominar técnicas de automatización funcional. Las principales lecciones aprendidas y prácticas implementadas fueron:

Page Object Model (POM): Implementar el POM desde el inicio permitió crear un código organizado, legible y fácilmente escalable. La separación entre los elementos de la página y la lógica de la prueba es vital para el mantenimiento.

Pruebas Data-Driven: El uso de DataProvider en TestNG nos enseñó a parametrizar las pruebas, lo que nos permite probar múltiples escenarios de registro con un solo método de prueba, maximizando la eficiencia.

Ejecución Cross-Browser: La configuración en testng.xml junto con WebDriverManager nos permitió ejecutar la suite en diferentes navegadores (Chrome y Firefox) sin necesidad de gestionar los drivers manualmente.

Generación de Evidencias: La implementación de un Listener de TestNG para capturar automáticamente capturas de pantalla en caso de fallo es una técnica esencial para la depuración y para la creación de reportes detallados.

Sincronización de Elementos: El uso de esperas explícitas con WebDriverWait fue crucial para manejar elementos dinámicos y evitar fallos intermitentes en la ejecución de las pruebas.

Entregables y Evidencias
Código Fuente: El proyecto completo, incluyendo los scripts de Selenium WebDriver, el archivo pom.xml, el testng.xml y las clases de utilidad, se encuentra en este repositorio.

Evidencias de Ejecución:
Capturas de pantalla: En caso de que una prueba falle, las capturas de pantalla se guardarán automáticamente en la carpeta target/screenshots/ para su análisis.
Reporte final: Tras la ejecución, se genera un informe HTML detallado en la carpeta target/surefire-reports/, el cual resume el estado de todas las pruebas.


 ## Análisis Técnico del Proyecto

### 1. Estructura de la Arquitectura
La organización del proyecto se adhiere a las convenciones de Maven, garantizando una estructura clara y un fácil mantenimiento.
* `src/test/java/com/tuempresa/`: Contiene las clases de pruebas principales (`LoginTest.java`, `RegistroTest.java`).
* `src/test/java/com/tuempresa/pages/`: Contiene las clases del **Page Object Model (POM)** (`LoginPage.java`, etc.), encapsulando los elementos y las interacciones de cada página.
* `src/test/resources/`: Almacena archivos de configuración y datos de prueba.

### 2. Configuración de Dependencias (`pom.xml`)
El archivo `pom.xml` está correctamente configurado para gestionar todas las dependencias del proyecto, garantizando una compilación y ejecución exitosa sin errores de dependencias.
* **`selenium-java` y `testng`:** Las dependencias core para la automatización y el framework de pruebas.
* **`webdrivermanager`:** Permite la ejecución de pruebas sin la necesidad de gestionar manualmente los drivers de navegadores.
* **`log4j-core` y `log4j-slf4j2-impl`:** Proporcionan una solución robusta para el logging, resolviendo la advertencia de SLF4J y permitiendo la generación de logs detallados.

### 3. Configuración de la Suite (`testng.xml`)
El archivo `testng.xml` demuestra una configuración avanzada y eficiente.
* **Paralelismo:** La suite está configurada para ejecutarse en paralelo con un `thread-count` de 2, lo que optimiza el tiempo de ejecución de los tests.
* **Ejecución Cross-Browser:** Utiliza un parámetro (`<parameter name="browser" value="chrome"/>`) que se pasa a las clases de tests, permitiendo cambiar el navegador de forma centralizada sin modificar el código.

---

## Análisis del Código y Buenas Prácticas

### 1. Implementación del Patrón POM
El proyecto sigue el patrón **Page Object Model**, lo que mejora la legibilidad y el mantenimiento del código.
* Las clases de páginas (`LoginPage`) encapsulan los localizadores de elementos (`@FindBy`) y los métodos de interacción.
* Las clases de prueba solo interactúan con estas clases de páginas, evitando la repetición de código y haciendo los tests más robustos.

### 2. Validación de Escenarios
El proyecto cumple con los siguientes requisitos funcionales de la consigna:
* **Registro de Usuario:** Se valida el flujo exitoso y los escenarios de fallo con campos inválidos.
* **Inicio de Sesión:** Se prueba el login con credenciales válidas e inválidas, y se valida el comportamiento de bloqueo de cuenta después de múltiples intentos fallidos.
* **Cross-Browser Testing:** El código está preparado para ejecutarse en Chrome y Firefox.

---

## Instrucciones de Ejecución
Para ejecutar la suite de pruebas, simplemente sigue estos pasos:

1.  Abre una terminal en la carpeta raíz del proyecto.
2.  Ejecuta el siguiente comando para compilar y correr todos los tests:
    ```bash
    mvn clean test
    ```

## Evidencias y Reportes
Después de la ejecución, Maven generará reportes detallados y evidencias en las siguientes ubicaciones:

* **Reporte HTML:** Para ver el resumen de la ejecución, abre el archivo `index.html` en tu navegador.
    ```
    target/surefire-reports/index.html
    ```
* *Evidencias de Ejecución:
Capturas de pantalla: En caso de que una prueba falle, las capturas de pantalla se guardarán automáticamente en la carpeta target/screenshots/ para su análisis.
Reporte final: Tras la ejecución, se genera un informe HTML detallado en la carpeta target/surefire-reports/, el cual resume el estado de todas las pruebas.

    ```


