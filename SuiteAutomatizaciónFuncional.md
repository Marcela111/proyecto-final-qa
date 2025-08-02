
Aquí tienes el contenido completo para tu archivo README.md, el cual cubre todos los puntos de la documentación técnica, la presentación final y los elementos para tu portafolio, sin que falte absolutamente nada.

Simplemente copia y pega todo este texto en un archivo llamado README.md en la raíz de tu proyecto.

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


  <title>TestNG reports</title>

    <link type="text/css" href="testng-reports1.css" rel="stylesheet" id="ultra" />
    <link type="text/css" href="testng-reports.css" rel="stylesheet" id="retro" disabled="false"/>
    <script type="text/javascript" src="jquery-3.6.0.min.js"></script>
    <script type="text/javascript" src="testng-reports.js"></script>
    <script type="text/javascript" src="https://www.google.com/jsapi"></script>
    <script type='text/javascript'>
      google.load('visualization', '1', {packages:['table']});
      google.setOnLoadCallback(drawTable);
      var suiteTableInitFunctions = new Array();
      var suiteTableData = new Array();
    </script>
    <!--
      <script type="text/javascript" src="jquery-ui/js/jquery-ui-1.8.16.custom.min.js"></script>
     -->
  </head>

  <body>    <div class="top-banner-root">
      <span class="top-banner-title-font">Test results</span>
      <button id="button" class="button">Switch Retro Theme</button> <!-- button -->
      <br/>
      <span class="top-banner-font-1">1 suite</span>
    </div> <!-- top-banner-root -->
    <div class="navigator-root">
      <div class="navigator-suite-header">
        <span>All suites</span>
        <a href="#" title="Collapse/expand all the suites" class="collapse-all-link">
          <img src="collapseall.gif" class="collapse-all-icon">
          </img> <!-- collapse-all-icon -->
        </a> <!-- collapse-all-link -->
      </div> <!-- navigator-suite-header -->
      <div class="suite">
        <div class="rounded-window">
          <div class="suite-header light-rounded-window-top">
            <a href="#" panel-name="suite-Suite_de_Automatizacion_Funcional" class="navigator-link">
              <span class="suite-name border-passed">Suite de Automatizacion Funcional</span>
            </a> <!-- navigator-link -->
          </div> <!-- suite-header light-rounded-window-top -->
          <div class="navigator-suite-content">
            <div class="suite-section-title">
              <span>Info</span>
            </div> <!-- suite-section-title -->
            <div class="suite-section-content">
              <ul>
                <li>
                  <a href="#" panel-name="test-xml-Suite_de_Automatizacion_Funcional" class="navigator-link ">
                    <span>C:\Users\mamor\OneDrive\Escritorio\tu-proyecto-de-automatizacion\testng.xml</span>
                  </a> <!-- navigator-link  -->
                </li>
                <li>
                  <a href="#" panel-name="testlist-Suite_de_Automatizacion_Funcional" class="navigator-link ">
                    <span class="test-stats">2 tests</span>
                  </a> <!-- navigator-link  -->
                </li>
                <li>
                  <a href="#" panel-name="group-Suite_de_Automatizacion_Funcional" class="navigator-link ">
                    <span>0 groups</span>
                  </a> <!-- navigator-link  -->
                </li>
                <li>
                  <a href="#" panel-name="times-Suite_de_Automatizacion_Funcional" class="navigator-link ">
                    <span>Times</span>
                  </a> <!-- navigator-link  -->
                </li>
                <li>
                  <a href="#" panel-name="reporter-Suite_de_Automatizacion_Funcional" class="navigator-link ">
                    <span>Reporter output</span>
                  </a> <!-- navigator-link  -->
                </li>
                <li>
                  <a href="#" panel-name="ignored-methods-Suite_de_Automatizacion_Funcional" class="navigator-link ">
                    <span>Ignored methods</span>
                  </a> <!-- navigator-link  -->
                </li>
                <li>
                  <a href="#" panel-name="chronological-Suite_de_Automatizacion_Funcional" class="navigator-link ">
                    <span>Chronological view</span>
                  </a> <!-- navigator-link  -->
                </li>
              </ul>
            </div> <!-- suite-section-content -->
            <div class="result-section">
              <div class="suite-section-title">
                <span>Results</span>
              </div> <!-- suite-section-title -->
              <div class="suite-section-content">
                <ul>
                  <li>
                    <span class="method-stats">18 methods,   18 passed</span>
                  </li>
                  <li>
                    <span class="method-list-title passed">Passed methods</span>
                    <span class="show-or-hide-methods passed">
                      <a href="#" panel-name="suite-Suite_de_Automatizacion_Funcional" class="hide-methods passed suite-Suite_de_Automatizacion_Funcional"> (hide)</a> <!-- hide-methods passed suite-Suite_de_Automatizacion_Funcional -->
                      <a href="#" panel-name="suite-Suite_de_Automatizacion_Funcional" class="show-methods passed suite-Suite_de_Automatizacion_Funcional"> (show)</a> <!-- show-methods passed suite-Suite_de_Automatizacion_Funcional -->
                    </span>
                    <div class="method-list-content passed suite-Suite_de_Automatizacion_Funcional">
                      <span>
                        <img src="passed.png" width="3%"/>
                        <a href="#" panel-name="suite-Suite_de_Automatizacion_Funcional" title="com.tuempresa.tests.LoginTest" class="method navigator-link" hash-for-method="testLoginExitoso">testLoginExitoso</a> <!-- method navigator-link -->
                      </span>
                      <br/>
                      <span>
                        <img src="passed.png" width="3%"/>
                        <a href="#" panel-name="suite-Suite_de_Automatizacion_Funcional" title="com.tuempresa.tests.LoginTest" class="method navigator-link" hash-for-method="testLoginExitoso">testLoginExitoso</a> <!-- method navigator-link -->
                      </span>
                      <br/>
                      <span>
                        <img src="passed.png" width="3%"/>
                        <a href="#" panel-name="suite-Suite_de_Automatizacion_Funcional" title="com.tuempresa.tests.LoginTest" class="method navigator-link" hash-for-method="testLoginFallido">testLoginFallido</a> <!-- method navigator-link -->
                      </span>
                      <br/>
                      <span>
                        <img src="passed.png" width="3%"/>
                        <a href="#" panel-name="suite-Suite_de_Automatizacion_Funcional" title="com.tuempresa.tests.LoginTest" class="method navigator-link" hash-for-method="testLoginFallido">testLoginFallido</a> <!-- method navigator-link -->
                      </span>
                      <br/>
                      <span>
                        <img src="passed.png" width="3%"/>
                        <a href="#" panel-name="suite-Suite_de_Automatizacion_Funcional" title="com.tuempresa.tests.LoginTest" class="method navigator-link" hash-for-method="testLoginFallidoMultiplesIntentos">testLoginFallidoMultiplesIntentos</a> <!-- method navigator-link -->
                      </span>
                      <br/>
                      <span>
                        <img src="passed.png" width="3%"/>
                        <a href="#" panel-name="suite-Suite_de_Automatizacion_Funcional" title="com.tuempresa.tests.LoginTest" class="method navigator-link" hash-for-method="testLoginFallidoMultiplesIntentos">testLoginFallidoMultiplesIntentos</a> <!-- method navigator-link -->
                      </span>
                      <br/>
                      <span>
                        <img src="passed.png" width="3%"/>
                        <a href="#" panel-name="suite-Suite_de_Automatizacion_Funcional" title="com.tuempresa.tests.RegistroTest" class="method navigator-link" hash-for-method="testRegistro(Juan, Perez, 1234567890, juan.perez@test.com, Pass1234!, Pass1234!, true)">testRegistro(Juan, Perez, 1234567890, juan.perez@test.com, Pass1234!, Pass1234!, true)</a> <!-- method navigator-link -->
                      </span>
                      <br/>
                      <span>
                        <img src="passed.png" width="3%"/>
                        <a href="#" panel-name="suite-Suite_de_Automatizacion_Funcional" title="com.tuempresa.tests.RegistroTest" class="method navigator-link" hash-for-method="testRegistro(Pedro, Sanchez, 4455667788, pedro.sanchez@test.com, pass123!, Pass1234!, false)">testRegistro(Pedro, Sanchez, 4455667788, pedro.sanchez@test.com, pass123!, Pass1234!, false)</a> <!-- method navigator-link -->
                      </span>
                      <br/>
                      <span>
                        <img src="passed.png" width="3%"/>
                        <a href="#" panel-name="suite-Suite_de_Automatizacion_Funcional" title="com.tuempresa.tests.RegistroTest" class="method navigator-link" hash-for-method="testRegistro(Sofia, Diaz, 1212121212, , TestPass123, TestPass123, true)">testRegistro(Sofia, Diaz, 1212121212, , TestPass123, TestPass123, true)</a> <!-- method navigator-link -->
                      </span>
                      <br/>
                      <span>
                        <img src="passed.png" width="3%"/>
                        <a href="#" panel-name="suite-Suite_de_Automatizacion_Funcional" title="com.tuempresa.tests.RegistroTest" class="method navigator-link" hash-for-method="testRegistro(, Rodriguez, 1122334455, rodrigo@test.com, SecurePass!, SecurePass!, true)">testRegistro(, Rodriguez, 1122334455, rodrigo@test.com, SecurePass!, SecurePass!, true)</a> <!-- method navigator-link -->
                      </span>
                      <br/>
                      <span>
                        <img src="passed.png" width="3%"/>
                        <a href="#" panel-name="suite-Suite_de_Automatizacion_Funcional" title="com.tuempresa.tests.RegistroTest" class="method navigator-link" hash-for-method="testRegistro(Ana, Lopez, 5566778899, ana.lopez@test.com, Pass123!, Pass123!, true)">testRegistro(Ana, Lopez, 5566778899, ana.lopez@test.com, Pass123!, Pass123!, true)</a> <!-- method navigator-link -->
                      </span>
                      <br/>
                      <span>
                        <img src="passed.png" width="3%"/>
                        <a href="#" panel-name="suite-Suite_de_Automatizacion_Funcional" title="com.tuempresa.tests.RegistroTest" class="method navigator-link" hash-for-method="testRegistro(Maria, Gomez, 9876543210, maria.gomez@test.com, pass123, pass123, true)">testRegistro(Maria, Gomez, 9876543210, maria.gomez@test.com, pass123, pass123, true)</a> <!-- method navigator-link -->
                      </span>
                      <br/>
                      <span>
                        <img src="passed.png" width="3%"/>
                        <a href="#" panel-name="suite-Suite_de_Automatizacion_Funcional" title="com.tuempresa.tests.RegistroTest" class="method navigator-link" hash-for-method="testRegistro(Pedro, Sanchez, 4455667788, pedro.sanchez@test.com, pass123!, Pass1234!, false)">testRegistro(Pedro, Sanchez, 4455667788, pedro.sanchez@test.com, pass123!, Pass1234!, false)</a> <!-- method navigator-link -->
                      </span>
                      <br/>
                      <span>
                        <img src="passed.png" width="3%"/>
                        <a href="#" panel-name="suite-Suite_de_Automatizacion_Funcional" title="com.tuempresa.tests.RegistroTest" class="method navigator-link" hash-for-method="testRegistro(Sofia, Diaz, 1212121212, , TestPass123, TestPass123, true)">testRegistro(Sofia, Diaz, 1212121212, , TestPass123, TestPass123, true)</a> <!-- method navigator-link -->
                      </span>
                      <br/>
                      <span>
                        <img src="passed.png" width="3%"/>
                        <a href="#" panel-name="suite-Suite_de_Automatizacion_Funcional" title="com.tuempresa.tests.RegistroTest" class="method navigator-link" hash-for-method="testRegistro(, Rodriguez, 1122334455, rodrigo@test.com, SecurePass!, SecurePass!, true)">testRegistro(, Rodriguez, 1122334455, rodrigo@test.com, SecurePass!, SecurePass!, true)</a> <!-- method navigator-link -->
                      </span>
                      <br/>
                      <span>
                        <img src="passed.png" width="3%"/>
                        <a href="#" panel-name="suite-Suite_de_Automatizacion_Funcional" title="com.tuempresa.tests.RegistroTest" class="method navigator-link" hash-for-method="testRegistro(Juan, Perez, 1234567890, juan.perez@test.com, Pass1234!, Pass1234!, true)">testRegistro(Juan, Perez, 1234567890, juan.perez@test.com, Pass1234!, Pass1234!, true)</a> <!-- method navigator-link -->
                      </span>
                      <br/>
                      <span>
                        <img src="passed.png" width="3%"/>
                        <a href="#" panel-name="suite-Suite_de_Automatizacion_Funcional" title="com.tuempresa.tests.RegistroTest" class="method navigator-link" hash-for-method="testRegistro(Maria, Gomez, 9876543210, maria.gomez@test.com, pass123, pass123, true)">testRegistro(Maria, Gomez, 9876543210, maria.gomez@test.com, pass123, pass123, true)</a> <!-- method navigator-link -->
                      </span>
                      <br/>
                      <span>
                        <img src="passed.png" width="3%"/>
                        <a href="#" panel-name="suite-Suite_de_Automatizacion_Funcional" title="com.tuempresa.tests.RegistroTest" class="method navigator-link" hash-for-method="testRegistro(Ana, Lopez, 5566778899, ana.lopez@test.com, Pass123!, Pass123!, true)">testRegistro(Ana, Lopez, 5566778899, ana.lopez@test.com, Pass123!, Pass123!, true)</a> <!-- method navigator-link -->
                      </span>
                      <br/>
                    </div> <!-- method-list-content passed suite-Suite_de_Automatizacion_Funcional -->
                  </li>
                </ul>
              </div> <!-- suite-section-content -->
            </div> <!-- result-section -->
          </div> <!-- navigator-suite-content -->
        </div> <!-- rounded-window -->
      </div> <!-- suite -->
    </div> <!-- navigator-root -->
    <div class="wrapper">
      <div class="main-panel-root">
        <div panel-name="suite-Suite_de_Automatizacion_Funcional" class="panel Suite_de_Automatizacion_Funcional">
          <div class="suite-Suite_de_Automatizacion_Funcional-class-passed">
            <div class="main-panel-header rounded-window-top">
              <img src="passed.png"/>
              <span class="class-name">com.tuempresa.tests.RegistroTest</span>
            </div> <!-- main-panel-header rounded-window-top -->
            <div class="main-panel-content rounded-window-bottom">
              <div class="method">
                <div class="method-content">
                  <a name="testRegistro(Juan, Perez, 1234567890, juan.perez@test.com, Pass1234!, Pass1234!, true)">
                  </a> <!-- testRegistro(Juan, Perez, 1234567890, juan.perez@test.com, Pass1234!, Pass1234!, true) -->
                  <span class="method-name">testRegistro</span>
                  <span class="parameters">(Juan,Perez,1234567890,juan.perez@test.com,Pass1234!,Pass1234!,true)</span>
                  <em>
(Valida el formulario de registro con diferentes datos.)                  </em>
                </div> <!-- method-content -->
              </div> <!-- method -->
              <div class="method">
                <div class="method-content">
                  <a name="testRegistro(Pedro, Sanchez, 4455667788, pedro.sanchez@test.com, pass123!, Pass1234!, false)">
                  </a> <!-- testRegistro(Pedro, Sanchez, 4455667788, pedro.sanchez@test.com, pass123!, Pass1234!, false) -->
                  <span class="method-name">testRegistro</span>
                  <span class="parameters">(Pedro,Sanchez,4455667788,pedro.sanchez@test.com,pass123!,Pass1234!,false)</span>
                  <em>
(Valida el formulario de registro con diferentes datos.)                  </em>
                </div> <!-- method-content -->
              </div> <!-- method -->
              <div class="method">
                <div class="method-content">
                  <a name="testRegistro(Sofia, Diaz, 1212121212, , TestPass123, TestPass123, true)">
                  </a> <!-- testRegistro(Sofia, Diaz, 1212121212, , TestPass123, TestPass123, true) -->
                  <span class="method-name">testRegistro</span>
                  <span class="parameters">(Sofia,Diaz,1212121212,,TestPass123,TestPass123,true)</span>
                  <em>
(Valida el formulario de registro con diferentes datos.)                  </em>
                </div> <!-- method-content -->
              </div> <!-- method -->
              <div class="method">
                <div class="method-content">
                  <a name="testRegistro(, Rodriguez, 1122334455, rodrigo@test.com, SecurePass!, SecurePass!, true)">
                  </a> <!-- testRegistro(, Rodriguez, 1122334455, rodrigo@test.com, SecurePass!, SecurePass!, true) -->
                  <span class="method-name">testRegistro</span>
                  <span class="parameters">(,Rodriguez,1122334455,rodrigo@test.com,SecurePass!,SecurePass!,true)</span>
                  <em>
(Valida el formulario de registro con diferentes datos.)                  </em>
                </div> <!-- method-content -->
              </div> <!-- method -->
              <div class="method">
                <div class="method-content">
                  <a name="testRegistro(Ana, Lopez, 5566778899, ana.lopez@test.com, Pass123!, Pass123!, true)">
                  </a> <!-- testRegistro(Ana, Lopez, 5566778899, ana.lopez@test.com, Pass123!, Pass123!, true) -->
                  <span class="method-name">testRegistro</span>
                  <span class="parameters">(Ana,Lopez,5566778899,ana.lopez@test.com,Pass123!,Pass123!,true)</span>
                  <em>
(Valida el formulario de registro con diferentes datos.)                  </em>
                </div> <!-- method-content -->
              </div> <!-- method -->
              <div class="method">
                <div class="method-content">
                  <a name="testRegistro(Maria, Gomez, 9876543210, maria.gomez@test.com, pass123, pass123, true)">
                  </a> <!-- testRegistro(Maria, Gomez, 9876543210, maria.gomez@test.com, pass123, pass123, true) -->
                  <span class="method-name">testRegistro</span>
                  <span class="parameters">(Maria,Gomez,9876543210,maria.gomez@test.com,pass123,pass123,true)</span>
                  <em>
(Valida el formulario de registro con diferentes datos.)                  </em>
                </div> <!-- method-content -->
              </div> <!-- method -->
              <div class="method">
                <div class="method-content">
                  <a name="testRegistro(Pedro, Sanchez, 4455667788, pedro.sanchez@test.com, pass123!, Pass1234!, false)">
                  </a> <!-- testRegistro(Pedro, Sanchez, 4455667788, pedro.sanchez@test.com, pass123!, Pass1234!, false) -->
                  <span class="method-name">testRegistro</span>
                  <span class="parameters">(Pedro,Sanchez,4455667788,pedro.sanchez@test.com,pass123!,Pass1234!,false)</span>
                  <em>
(Valida el formulario de registro con diferentes datos.)                  </em>
                </div> <!-- method-content -->
              </div> <!-- method -->
              <div class="method">
                <div class="method-content">
                  <a name="testRegistro(Sofia, Diaz, 1212121212, , TestPass123, TestPass123, true)">
                  </a> <!-- testRegistro(Sofia, Diaz, 1212121212, , TestPass123, TestPass123, true) -->
                  <span class="method-name">testRegistro</span>
                  <span class="parameters">(Sofia,Diaz,1212121212,,TestPass123,TestPass123,true)</span>
                  <em>
(Valida el formulario de registro con diferentes datos.)                  </em>
                </div> <!-- method-content -->
              </div> <!-- method -->
              <div class="method">
                <div class="method-content">
                  <a name="testRegistro(, Rodriguez, 1122334455, rodrigo@test.com, SecurePass!, SecurePass!, true)">
                  </a> <!-- testRegistro(, Rodriguez, 1122334455, rodrigo@test.com, SecurePass!, SecurePass!, true) -->
                  <span class="method-name">testRegistro</span>
                  <span class="parameters">(,Rodriguez,1122334455,rodrigo@test.com,SecurePass!,SecurePass!,true)</span>
                  <em>
(Valida el formulario de registro con diferentes datos.)                  </em>
                </div> <!-- method-content -->
              </div> <!-- method -->
              <div class="method">
                <div class="method-content">
                  <a name="testRegistro(Juan, Perez, 1234567890, juan.perez@test.com, Pass1234!, Pass1234!, true)">
                  </a> <!-- testRegistro(Juan, Perez, 1234567890, juan.perez@test.com, Pass1234!, Pass1234!, true) -->
                  <span class="method-name">testRegistro</span>
                  <span class="parameters">(Juan,Perez,1234567890,juan.perez@test.com,Pass1234!,Pass1234!,true)</span>
                  <em>
(Valida el formulario de registro con diferentes datos.)                  </em>
                </div> <!-- method-content -->
              </div> <!-- method -->
              <div class="method">
                <div class="method-content">
                  <a name="testRegistro(Maria, Gomez, 9876543210, maria.gomez@test.com, pass123, pass123, true)">
                  </a> <!-- testRegistro(Maria, Gomez, 9876543210, maria.gomez@test.com, pass123, pass123, true) -->
                  <span class="method-name">testRegistro</span>
                  <span class="parameters">(Maria,Gomez,9876543210,maria.gomez@test.com,pass123,pass123,true)</span>
                  <em>
(Valida el formulario de registro con diferentes datos.)                  </em>
                </div> <!-- method-content -->
              </div> <!-- method -->
              <div class="method">
                <div class="method-content">
                  <a name="testRegistro(Ana, Lopez, 5566778899, ana.lopez@test.com, Pass123!, Pass123!, true)">
                  </a> <!-- testRegistro(Ana, Lopez, 5566778899, ana.lopez@test.com, Pass123!, Pass123!, true) -->
                  <span class="method-name">testRegistro</span>
                  <span class="parameters">(Ana,Lopez,5566778899,ana.lopez@test.com,Pass123!,Pass123!,true)</span>
                  <em>
(Valida el formulario de registro con diferentes datos.)                  </em>
                </div> <!-- method-content -->
              </div> <!-- method -->
            </div> <!-- main-panel-content rounded-window-bottom -->
          </div> <!-- suite-Suite_de_Automatizacion_Funcional-class-passed -->
          <div class="suite-Suite_de_Automatizacion_Funcional-class-passed">
            <div class="main-panel-header rounded-window-top">
              <img src="passed.png"/>
              <span class="class-name">com.tuempresa.tests.LoginTest</span>
            </div> <!-- main-panel-header rounded-window-top -->
            <div class="main-panel-content rounded-window-bottom">
              <div class="method">
                <div class="method-content">
                  <a name="testLoginExitoso">
                  </a> <!-- testLoginExitoso -->
                  <span class="method-name">testLoginExitoso</span>
                  <em>
(Verificar login con credenciales válidas)                  </em>
                </div> <!-- method-content -->
              </div> <!-- method -->
              <div class="method">
                <div class="method-content">
                  <a name="testLoginExitoso">
                  </a> <!-- testLoginExitoso -->
                  <span class="method-name">testLoginExitoso</span>
                  <em>
(Verificar login con credenciales válidas)                  </em>
                </div> <!-- method-content -->
              </div> <!-- method -->
              <div class="method">
                <div class="method-content">
                  <a name="testLoginFallido">
                  </a> <!-- testLoginFallido -->
                  <span class="method-name">testLoginFallido</span>
                  <em>
(Verificar login con credenciales inválidas)                  </em>
                </div> <!-- method-content -->
              </div> <!-- method -->
              <div class="method">
                <div class="method-content">
                  <a name="testLoginFallido">
                  </a> <!-- testLoginFallido -->
                  <span class="method-name">testLoginFallido</span>
                  <em>
(Verificar login con credenciales inválidas)                  </em>
                </div> <!-- method-content -->
              </div> <!-- method -->
              <div class="method">
                <div class="method-content">
                  <a name="testLoginFallidoMultiplesIntentos">
                  </a> <!-- testLoginFallidoMultiplesIntentos -->
                  <span class="method-name">testLoginFallidoMultiplesIntentos</span>
                  <em>
(Verificar comportamiento con múltiples fallas)                  </em>
                </div> <!-- method-content -->
              </div> <!-- method -->
              <div class="method">
                <div class="method-content">
                  <a name="testLoginFallidoMultiplesIntentos">
                  </a> <!-- testLoginFallidoMultiplesIntentos -->
                  <span class="method-name">testLoginFallidoMultiplesIntentos</span>
                  <em>
(Verificar comportamiento con múltiples fallas)                  </em>
                </div> <!-- method-content -->
              </div> <!-- method -->
            </div> <!-- main-panel-content rounded-window-bottom -->
          </div> <!-- suite-Suite_de_Automatizacion_Funcional-class-passed -->
        </div> <!-- panel Suite_de_Automatizacion_Funcional -->
        <div panel-name="test-xml-Suite_de_Automatizacion_Funcional" class="panel">
          <div class="main-panel-header rounded-window-top">
            <span class="header-content">C:\Users\mamor\OneDrive\Escritorio\tu-proyecto-de-automatizacion\testng.xml</span>
          </div> <!-- main-panel-header rounded-window-top -->
          <div class="main-panel-content rounded-window-bottom">
            <pre>
&lt;?xml version=&quot;1.0&quot; encoding=&quot;UTF-8&quot;?&gt;
&lt;!DOCTYPE suite SYSTEM &quot;https://testng.org/testng-1.0.dtd&quot;&gt;
&lt;suite name=&quot;Suite de Automatizacion Funcional&quot; guice-stage=&quot;DEVELOPMENT&quot; verbose=&quot;0&quot;&gt;
  &lt;listeners&gt;
    &lt;listener class-name=&quot;com.tuempresa.utils.ScreenshotListener&quot;/&gt;
  &lt;/listeners&gt;
  &lt;test thread-count=&quot;5&quot; name=&quot;Ejecucion en Chrome&quot; verbose=&quot;0&quot;&gt;
    &lt;parameter name=&quot;browser&quot; value=&quot;chrome&quot;/&gt;
    &lt;classes&gt;
      &lt;class name=&quot;com.tuempresa.tests.LoginTest&quot;/&gt;
      &lt;class name=&quot;com.tuempresa.tests.RegistroTest&quot;/&gt;
    &lt;/classes&gt;
  &lt;/test&gt; &lt;!-- Ejecucion en Chrome --&gt;
  &lt;test thread-count=&quot;5&quot; name=&quot;Ejecucion en Firefox&quot; verbose=&quot;0&quot;&gt;
    &lt;parameter name=&quot;browser&quot; value=&quot;firefox&quot;/&gt;
    &lt;classes&gt;
      &lt;class name=&quot;com.tuempresa.tests.LoginTest&quot;/&gt;
      &lt;class name=&quot;com.tuempresa.tests.RegistroTest&quot;/&gt;
    &lt;/classes&gt;
  &lt;/test&gt; &lt;!-- Ejecucion en Firefox --&gt;
&lt;/suite&gt; &lt;!-- Suite de Automatizacion Funcional --&gt;
            </pre>
          </div> <!-- main-panel-content rounded-window-bottom -->
        </div> <!-- panel -->
        <div panel-name="testlist-Suite_de_Automatizacion_Funcional" class="panel">
          <div class="main-panel-header rounded-window-top">
            <span class="header-content">Tests for Suite de Automatizacion Funcional</span>
          </div> <!-- main-panel-header rounded-window-top -->
          <div class="main-panel-content rounded-window-bottom">
            <ul>
              <li>
                <span class="test-name">Ejecucion en Chrome (2 classes)</span>
              </li>
              <li>
                <span class="test-name">Ejecucion en Firefox (2 classes)</span>
              </li>
            </ul>
          </div> <!-- main-panel-content rounded-window-bottom -->
        </div> <!-- panel -->
        <div panel-name="group-Suite_de_Automatizacion_Funcional" class="panel">
          <div class="main-panel-header rounded-window-top">
            <span class="header-content">Groups for Suite de Automatizacion Funcional</span>
          </div> <!-- main-panel-header rounded-window-top -->
          <div class="main-panel-content rounded-window-bottom">
          </div> <!-- main-panel-content rounded-window-bottom -->
        </div> <!-- panel -->
        <div panel-name="times-Suite_de_Automatizacion_Funcional" class="panel">
          <div class="main-panel-header rounded-window-top">
            <span class="header-content">Times for Suite de Automatizacion Funcional</span>
          </div> <!-- main-panel-header rounded-window-top -->
          <div class="main-panel-content rounded-window-bottom">
            <div class="times-div">
              <script type="text/javascript">
suiteTableInitFunctions.push('tableData_Suite_de_Automatizacion_Funcional');
function tableData_Suite_de_Automatizacion_Funcional() {
var data = new google.visualization.DataTable();
data.addColumn('number', 'Number');
data.addColumn('string', 'Method');
data.addColumn('string', 'Class');
data.addColumn('number', 'Time (ms)');
data.addRows(18);
data.setCell(0, 0, 0)
data.setCell(0, 1, 'testRegistro')
data.setCell(0, 2, 'com.tuempresa.tests.RegistroTest')
data.setCell(0, 3, 14655);
data.setCell(1, 0, 1)
data.setCell(1, 1, 'testRegistro')
data.setCell(1, 2, 'com.tuempresa.tests.RegistroTest')
data.setCell(1, 3, 13826);
data.setCell(2, 0, 2)
data.setCell(2, 1, 'testLoginFallidoMultiplesIntentos')
data.setCell(2, 2, 'com.tuempresa.tests.LoginTest')
data.setCell(2, 3, 6062);
data.setCell(3, 0, 3)
data.setCell(3, 1, 'testLoginFallidoMultiplesIntentos')
data.setCell(3, 2, 'com.tuempresa.tests.LoginTest')
data.setCell(3, 3, 5695);
data.setCell(4, 0, 4)
data.setCell(4, 1, 'testRegistro')
data.setCell(4, 2, 'com.tuempresa.tests.RegistroTest')
data.setCell(4, 3, 4842);
data.setCell(5, 0, 5)
data.setCell(5, 1, 'testRegistro')
data.setCell(5, 2, 'com.tuempresa.tests.RegistroTest')
data.setCell(5, 3, 4525);
data.setCell(6, 0, 6)
data.setCell(6, 1, 'testLoginExitoso')
data.setCell(6, 2, 'com.tuempresa.tests.LoginTest')
data.setCell(6, 3, 4518);
data.setCell(7, 0, 7)
data.setCell(7, 1, 'testLoginExitoso')
data.setCell(7, 2, 'com.tuempresa.tests.LoginTest')
data.setCell(7, 3, 4409);
data.setCell(8, 0, 8)
data.setCell(8, 1, 'testLoginFallido')
data.setCell(8, 2, 'com.tuempresa.tests.LoginTest')
data.setCell(8, 3, 4162);
data.setCell(9, 0, 9)
data.setCell(9, 1, 'testLoginFallido')
data.setCell(9, 2, 'com.tuempresa.tests.LoginTest')
data.setCell(9, 3, 4077);
data.setCell(10, 0, 10)
data.setCell(10, 1, 'testRegistro')
data.setCell(10, 2, 'com.tuempresa.tests.RegistroTest')
data.setCell(10, 3, 4011);
data.setCell(11, 0, 11)
data.setCell(11, 1, 'testRegistro')
data.setCell(11, 2, 'com.tuempresa.tests.RegistroTest')
data.setCell(11, 3, 4000);
data.setCell(12, 0, 12)
data.setCell(12, 1, 'testRegistro')
data.setCell(12, 2, 'com.tuempresa.tests.RegistroTest')
data.setCell(12, 3, 3979);
data.setCell(13, 0, 13)
data.setCell(13, 1, 'testRegistro')
data.setCell(13, 2, 'com.tuempresa.tests.RegistroTest')
data.setCell(13, 3, 3921);
data.setCell(14, 0, 14)
data.setCell(14, 1, 'testRegistro')
data.setCell(14, 2, 'com.tuempresa.tests.RegistroTest')
data.setCell(14, 3, 3866);
data.setCell(15, 0, 15)
data.setCell(15, 1, 'testRegistro')
data.setCell(15, 2, 'com.tuempresa.tests.RegistroTest')
data.setCell(15, 3, 3828);
data.setCell(16, 0, 16)
data.setCell(16, 1, 'testRegistro')
data.setCell(16, 2, 'com.tuempresa.tests.RegistroTest')
data.setCell(16, 3, 3713);
data.setCell(17, 0, 17)
data.setCell(17, 1, 'testRegistro')
data.setCell(17, 2, 'com.tuempresa.tests.RegistroTest')
data.setCell(17, 3, 3646);
window.suiteTableData['Suite_de_Automatizacion_Funcional']= { tableData: data, tableDiv: 'times-div-Suite_de_Automatizacion_Funcional'}
return data;
}
              </script>
              <span class="suite-total-time">Total running time: 1 minutes</span>
              <div id="times-div-Suite_de_Automatizacion_Funcional">
              </div> <!-- times-div-Suite_de_Automatizacion_Funcional -->
            </div> <!-- times-div -->
          </div> <!-- main-panel-content rounded-window-bottom -->
        </div> <!-- panel -->
        <div panel-name="reporter-Suite_de_Automatizacion_Funcional" class="panel">
          <div class="main-panel-header rounded-window-top">
            <span class="header-content">Reporter output for Suite de Automatizacion Funcional</span>
          </div> <!-- main-panel-header rounded-window-top -->
          <div class="main-panel-content rounded-window-bottom">
          </div> <!-- main-panel-content rounded-window-bottom -->
        </div> <!-- panel -->
        <div panel-name="ignored-methods-Suite_de_Automatizacion_Funcional" class="panel">
          <div class="main-panel-header rounded-window-top">
            <span class="header-content">0 ignored methods</span>
          </div> <!-- main-panel-header rounded-window-top -->
          <div class="main-panel-content rounded-window-bottom">
          </div> <!-- main-panel-content rounded-window-bottom -->
        </div> <!-- panel -->
        <div panel-name="chronological-Suite_de_Automatizacion_Funcional" class="panel">
          <div class="main-panel-header rounded-window-top">
            <span class="header-content">Methods in chronological order</span>
          </div> <!-- main-panel-header rounded-window-top -->
          <div class="main-panel-content rounded-window-bottom">
            <div class="chronological-class">
              <div class="chronological-class-name">com.tuempresa.tests.LoginTest</div> <!-- chronological-class-name -->
              <div class="configuration-method before">
                <span class="method-name">setup(chrome)</span>
                <span class="method-start">0 ms</span>
              </div> <!-- configuration-method before -->
              <div class="test-method">
                <span class="method-name">testLoginExitoso</span>
                <span class="method-start">1794 ms</span>
              </div> <!-- test-method -->
              <div class="configuration-method after">
                <span class="method-name">teardown</span>
                <span class="method-start">6315 ms</span>
              </div> <!-- configuration-method after -->
              <div class="configuration-method before">
                <span class="method-name">setup(chrome)</span>
                <span class="method-start">6524 ms</span>
              </div> <!-- configuration-method before -->
              <div class="test-method">
                <span class="method-name">testLoginFallido</span>
                <span class="method-start">7403 ms</span>
              </div> <!-- test-method -->
              <div class="configuration-method after">
                <span class="method-name">teardown</span>
                <span class="method-start">11567 ms</span>
              </div> <!-- configuration-method after -->
              <div class="configuration-method before">
                <span class="method-name">setup(chrome)</span>
                <span class="method-start">11782 ms</span>
              </div> <!-- configuration-method before -->
              <div class="test-method">
                <span class="method-name">testLoginFallidoMultiplesIntentos</span>
                <span class="method-start">12555 ms</span>
              </div> <!-- test-method -->
              <div class="configuration-method after">
                <span class="method-name">teardown</span>
                <span class="method-start">18250 ms</span>
              </div> <!-- configuration-method after -->
            </div> <!-- chronological-class -->
            <div class="chronological-class">
              <div class="chronological-class-name">com.tuempresa.tests.RegistroTest</div> <!-- chronological-class-name -->
              <div class="configuration-method before">
                <span class="method-name">setup(chrome)</span>
                <span class="method-start">18477 ms</span>
              </div> <!-- configuration-method before -->
              <div class="test-method">
                <span class="method-name">testRegistro(Juan, Perez, 1234567890, juan.perez@test.com, Pass1234!, Pass1234!, true)</span>
                <span class="method-start">19252 ms</span>
              </div> <!-- test-method -->
              <div class="configuration-method after">
                <span class="method-name">teardown</span>
                <span class="method-start">23231 ms</span>
              </div> <!-- configuration-method after -->
              <div class="configuration-method before">
                <span class="method-name">setup(chrome)</span>
                <span class="method-start">23493 ms</span>
              </div> <!-- configuration-method before -->
              <div class="test-method">
                <span class="method-name">testRegistro(Maria, Gomez, 9876543210, maria.gomez@test.com, pass123, pass123, true)</span>
                <span class="method-start">24300 ms</span>
              </div> <!-- test-method -->
              <div class="configuration-method after">
                <span class="method-name">teardown</span>
                <span class="method-start">28014 ms</span>
              </div> <!-- configuration-method after -->
              <div class="configuration-method before">
                <span class="method-name">setup(chrome)</span>
                <span class="method-start">28241 ms</span>
              </div> <!-- configuration-method before -->
              <div class="test-method">
                <span class="method-name">testRegistro(, Rodriguez, 1122334455, rodrigo@test.com, SecurePass!, SecurePass!, true)</span>
                <span class="method-start">29044 ms</span>
              </div> <!-- test-method -->
              <div class="configuration-method after">
                <span class="method-name">teardown</span>
                <span class="method-start">32965 ms</span>
              </div> <!-- configuration-method after -->
              <div class="configuration-method before">
                <span class="method-name">setup(chrome)</span>
                <span class="method-start">33167 ms</span>
              </div> <!-- configuration-method before -->
              <div class="test-method">
                <span class="method-name">testRegistro(Ana, Lopez, 5566778899, ana.lopez@test.com, Pass123!, Pass123!, true)</span>
                <span class="method-start">34046 ms</span>
              </div> <!-- test-method -->
              <div class="configuration-method after">
                <span class="method-name">teardown</span>
                <span class="method-start">38057 ms</span>
              </div> <!-- configuration-method after -->
              <div class="configuration-method before">
                <span class="method-name">setup(chrome)</span>
                <span class="method-start">38266 ms</span>
              </div> <!-- configuration-method before -->
              <div class="test-method">
                <span class="method-name">testRegistro(Sofia, Diaz, 1212121212, , TestPass123, TestPass123, true)</span>
                <span class="method-start">39065 ms</span>
              </div> <!-- test-method -->
              <div class="configuration-method after">
                <span class="method-name">teardown</span>
                <span class="method-start">42712 ms</span>
              </div> <!-- configuration-method after -->
              <div class="configuration-method before">
                <span class="method-name">setup(chrome)</span>
                <span class="method-start">42922 ms</span>
              </div> <!-- configuration-method before -->
              <div class="test-method">
                <span class="method-name">testRegistro(Pedro, Sanchez, 4455667788, pedro.sanchez@test.com, pass123!, Pass1234!, false)</span>
                <span class="method-start">43782 ms</span>
              </div> <!-- test-method -->
              <div class="configuration-method after">
                <span class="method-name">teardown</span>
                <span class="method-start">58437 ms</span>
              </div> <!-- configuration-method after -->
            </div> <!-- chronological-class -->
            <div class="chronological-class">
              <div class="chronological-class-name">com.tuempresa.tests.LoginTest</div> <!-- chronological-class-name -->
              <div class="configuration-method before">
                <span class="method-name">setup(firefox)</span>
                <span class="method-start">58778 ms</span>
              </div> <!-- configuration-method before -->
              <div class="test-method">
                <span class="method-name">testLoginExitoso</span>
                <span class="method-start">63021 ms</span>
              </div> <!-- test-method -->
              <div class="configuration-method after">
                <span class="method-name">teardown</span>
                <span class="method-start">67431 ms</span>
              </div> <!-- configuration-method after -->
              <div class="configuration-method before">
                <span class="method-name">setup(firefox)</span>
                <span class="method-start">70613 ms</span>
              </div> <!-- configuration-method before -->
              <div class="test-method">
                <span class="method-name">testLoginFallido</span>
                <span class="method-start">74865 ms</span>
              </div> <!-- test-method -->
              <div class="configuration-method after">
                <span class="method-name">teardown</span>
                <span class="method-start">78944 ms</span>
              </div> <!-- configuration-method after -->
              <div class="configuration-method before">
                <span class="method-name">setup(firefox)</span>
                <span class="method-start">82299 ms</span>
              </div> <!-- configuration-method before -->
              <div class="test-method">
                <span class="method-name">testLoginFallidoMultiplesIntentos</span>
                <span class="method-start">86538 ms</span>
              </div> <!-- test-method -->
              <div class="configuration-method after">
                <span class="method-name">teardown</span>
                <span class="method-start">92601 ms</span>
              </div> <!-- configuration-method after -->
            </div> <!-- chronological-class -->
            <div class="chronological-class">
              <div class="chronological-class-name">com.tuempresa.tests.RegistroTest</div> <!-- chronological-class-name -->
              <div class="configuration-method before">
                <span class="method-name">setup(firefox)</span>
                <span class="method-start">95843 ms</span>
              </div> <!-- configuration-method before -->
              <div class="test-method">
                <span class="method-name">testRegistro(Juan, Perez, 1234567890, juan.perez@test.com, Pass1234!, Pass1234!, true)</span>
                <span class="method-start">100133 ms</span>
              </div> <!-- test-method -->
              <div class="configuration-method after">
                <span class="method-name">teardown</span>
                <span class="method-start">104976 ms</span>
              </div> <!-- configuration-method after -->
              <div class="configuration-method before">
                <span class="method-name">setup(firefox)</span>
                <span class="method-start">108189 ms</span>
              </div> <!-- configuration-method before -->
              <div class="test-method">
                <span class="method-name">testRegistro(Maria, Gomez, 9876543210, maria.gomez@test.com, pass123, pass123, true)</span>
                <span class="method-start">112545 ms</span>
              </div> <!-- test-method -->
              <div class="configuration-method after">
                <span class="method-name">teardown</span>
                <span class="method-start">117070 ms</span>
              </div> <!-- configuration-method after -->
              <div class="configuration-method before">
                <span class="method-name">setup(firefox)</span>
                <span class="method-start">120265 ms</span>
              </div> <!-- configuration-method before -->
              <div class="test-method">
                <span class="method-name">testRegistro(, Rodriguez, 1122334455, rodrigo@test.com, SecurePass!, SecurePass!, true)</span>
                <span class="method-start">124562 ms</span>
              </div> <!-- test-method -->
              <div class="configuration-method after">
                <span class="method-name">teardown</span>
                <span class="method-start">128428 ms</span>
              </div> <!-- configuration-method after -->
              <div class="configuration-method before">
                <span class="method-name">setup(firefox)</span>
                <span class="method-start">131640 ms</span>
              </div> <!-- configuration-method before -->
              <div class="test-method">
                <span class="method-name">testRegistro(Ana, Lopez, 5566778899, ana.lopez@test.com, Pass123!, Pass123!, true)</span>
                <span class="method-start">135899 ms</span>
              </div> <!-- test-method -->
              <div class="configuration-method after">
                <span class="method-name">teardown</span>
                <span class="method-start">139728 ms</span>
              </div> <!-- configuration-method after -->
              <div class="configuration-method before">
                <span class="method-name">setup(firefox)</span>
                <span class="method-start">142963 ms</span>
              </div> <!-- configuration-method before -->
              <div class="test-method">
                <span class="method-name">testRegistro(Sofia, Diaz, 1212121212, , TestPass123, TestPass123, true)</span>
                <span class="method-start">147350 ms</span>
              </div> <!-- test-method -->
              <div class="configuration-method after">
                <span class="method-name">teardown</span>
                <span class="method-start">151350 ms</span>
              </div> <!-- configuration-method after -->
              <div class="configuration-method before">
                <span class="method-name">setup(firefox)</span>
                <span class="method-start">154716 ms</span>
              </div> <!-- configuration-method before -->
              <div class="test-method">
                <span class="method-name">testRegistro(Pedro, Sanchez, 4455667788, pedro.sanchez@test.com, pass123!, Pass1234!, false)</span>
                <span class="method-start">158982 ms</span>
              </div> <!-- test-method -->
              <div class="configuration-method after">
                <span class="method-name">teardown</span>
                <span class="method-start">172809 ms</span>
              </div> <!-- configuration-method after -->
          </div> <!-- main-panel-content rounded-window-bottom -->
        </div> <!-- panel -->
      </div> <!-- main-panel-root -->
    </div> <!-- wrapper -->
  </body>
<script type="text/javascript" src="testng-reports2.js"></script>
</html>


