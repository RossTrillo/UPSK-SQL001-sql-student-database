# UPSK-SQL001 SQL Student Database

En el segundo tutorial de este proyecto, profundicé en la administración y análisis de bases de datos de estudiantes utilizando **SQL** y **PostgreSQL**. Aprendí a realizar consultas avanzadas, a manejar bases de datos y a utilizar scripts Bash para automatizar tareas.

## Contenidos del Tutorial

### 1. Consultas Avanzadas en SQL
- **JOIN**: Combina datos de múltiples tablas.
- **GROUP BY y HAVING**: Agrupa y filtra datos agregados.
- **ORDER BY**: Ordena los resultados de las consultas.
- **Funciones de Agregación**: Utilización de `COUNT`, `SUM`, `AVG`, `MAX`, y `MIN` para resumir datos.
- **ALTER TABLE**: Modificación de estructuras de tablas existentes.

### 2. Administración de Bases de Datos
- **Copia de Seguridad y Restauración**: Aprenderás a crear copias de seguridad y a restaurarlas utilizando PostgreSQL.
- **Shell Scripts**: Uso de scripts Bash para la gestión eficiente y segura de tu entorno.

## Comandos Utilizados

```bash
# Listar las bases de datos.
\l

# Reconstruir la base de datos desde un archivo SQL.
psql -U postgres < students.sql

# Conectarse a la base de datos 'students'.
\c students

# Mostrar las tablas y relaciones existentes.
\d

# Verificar los datos en la tabla 'students'.
SELECT * FROM students;

# Crear un script Bash para mostrar información de los estudiantes.
touch student_info.sh

# Dar permisos de ejecución al script.
chmod +x student_info.sh

# Añadir un comentario y un shebang al script.
echo -e "#!/bin/bash\n# Info about my computer science students from students database" > student_info.sh

# Ejecutar el script.
./student_info.sh

# Consultar datos específicos usando SQL en el script.
PSQL="psql -X --username=freecodecamp --dbname=students --no-align --tuples-only -c"
echo -e "\nFirst name, last name, and GPA of students with a 4.0 GPA:"
echo "$($PSQL "SELECT first_name, last_name, gpa FROM students WHERE gpa = 4.0")"
