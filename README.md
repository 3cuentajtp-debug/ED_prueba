# Pruebas unitarias

Pruebas automáticas de SmartCare CNS. Cada prueba ejecuta una función del sistema, compara el resultado con lo esperado e imprime en la terminal si fue **exitosa** o **fallida**, junto con los datos que devolvió.

Se ejecutan por terminal, no desde el navegador.

## Cómo ejecutarlas

Abre una terminal (CMD) en la carpeta raíz del proyecto y ejecuta:

```bash
C:\xampp\php\php.exe tests\run_all.php
```

Para ejecutar un solo archivo:

```bash
C:\xampp\php\php.exe tests\test_login.php
```

Si los acentos se ven mal en CMD, ejecuta antes `chcp 65001`.

## Archivos

| Archivo | Qué prueba |
|---|---|
| `run_all.php` | Ejecuta todas las pruebas y muestra el resumen final |
| `Prueba.php` | Clase auxiliar que compara resultados e imprime el reporte |
| `test_registro_paciente.php` | Validaciones del registro de pacientes |
| `test_login.php` | Inicio de sesión |
| `test_filtros_y_horarios.php` | Filtros de reportes y generación de horarios |

## Resultado esperado

Cada prueba muestra una línea como esta:

```
[OK]    PRUEBA EXITOSA: Menor de edad es rechazado
        Devuelve: {"fecha_nac":"Debes ser mayor de 18 años."}
```

Si una falla, se muestra lo esperado y lo obtenido:

```
[FALLO] PRUEBA FALLIDA: nombre de la prueba
        Esperado: ...
        Obtenido: ...
```

Al final aparece el resumen:

```
RESULTADO: 43 pruebas | 43 exitosas | 0 fallidas
```

## Agregar una prueba nueva

1. Crea un archivo `test_nombre.php` en esta carpeta.
2. Al inicio, incluye el ayudante: `require_once __DIR__ . '/Prueba.php';`
3. Escribe cada caso con `Prueba::caso('Qué se prueba', $esperado, $obtenido);`
4. Añade `require __DIR__ . '/test_nombre.php';` en `run_all.php`.
