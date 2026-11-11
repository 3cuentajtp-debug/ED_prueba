# SmartCare CNS

Sistema web de gestión de citas médicas para la Caja Nacional de Salud (CNS), hecho con **PHP** y **MySQL**. Tiene paneles para cuatro roles: paciente, médico, administrador y recepcionista, y un chatbot opcional con IA.

## Instalación

1. Clonar el proyecto dentro de `htdocs`:
   ```bash
   cd C:\xampp\htdocs
   git clone https://github.com/Valerfy/proyecto_smartcare.git
   ```
2. Abrir XAMPP e iniciar **Apache** y **MySQL**.
3. En http://localhost/phpmyadmin/ crear una base de datos llamada `cns_sistema_v2`.
4. Entrar a esa base, ir a **Importar** y cargar `database/cns_sistema_v2.sql`.
5. Abrir http://localhost/proyecto_smartcare/public/

La conexión a la base de datos se configura en `config/conexion.php` (por defecto: usuario `root`, sin contraseña).

## Cuentas de prueba

Contraseña de todas: `1234`

| Rol | Correo |
|---|---|
| Paciente | valerofernandezmatias@gmail.com |
| Médico | anuar.vargas@cns.org.bo |
| Administrador | matias.valero@cns.com |
| Recepcionista | sofia.loayza@cns.rec.bo |

> Solo para uso en entorno local.

## Pruebas unitarias

Están en la carpeta `tests/` y se ejecutan por terminal, no desde el navegador.

Desde la raíz del proyecto:
```bash
C:\xampp\php\php.exe tests\run_all.php
```

| Archivo | Qué prueba |
|---|---|
| `test_registro_paciente.php` | Validaciones del registro de pacientes |
| `test_login.php` | Inicio de sesión |
| `test_filtros_y_horarios.php` | Filtros de reportes y generación de horarios |
| `run_all.php` | Ejecuta todas y muestra el resumen |

Si los acentos se ven mal en CMD, ejecutar antes `chcp 65001`.

## Chatbot (opcional)

1. Instalar Ollama.
2. Descargar el modelo: `ollama pull qwen3:4b`
3. Dejar Ollama en ejecución.

El resto del sistema funciona sin el chatbot.

## Estructura

```
assets/        CSS, JavaScript e imágenes
config/        Conexión a la base de datos
controllers/   Lógica de cada rol
database/      Script SQL con datos de prueba
models/        Acceso a datos
public/        Punto de entrada (index.php)
tests/         Pruebas unitarias
views/         Vistas por rol
```

## Integrantes

- Matías Valero Fernández ([@Valerfy](https://github.com/Valerfy))
- Juan Anuar Vargas Claros ([@Anufox](https://github.com/Anufox))
- Jhonatan Torrez Pocoma
