Crear Base de Datos 
> DBCA

Crear Listener
> NETCA
( Nombre/puerto )

Arrancar Entreprise manager
> w


Gesion de ususarios
  servidor/gestion de usuarios
 - perfiles
 - roles
 - cuentas



Respaldo
- Modo ArchiveLog
1.- nano /u01/app/oracle/product/11.2.0/db_1/dbs/init.ora
2.- una vez en init agregar estas lineas debajo
log_archive_start = true
log_archive_dest_1 = “location=/database/archivelog/bbdd REOPEN=5"
log_archive_format = arch_%t_%s.arc
3.- Ingresar a SQLPLUS con comando sqlplus / as sysdba
4.- shutdown immediate
5.- startup mount
6.- alter database archivelog;
7.- alter database open;
8.- alter system archive log start;
9.- archive Log list
10.- se revisa si esta en modo archive log


- Multiplexar Archivos de control /redolog
    Ruta / / / / 
      |-> Modificar Archivos Parametro --> Init.ora
                                       |-> Spfile.ora
                                       |-> Crear Pfile a partir de un Spfile

Multiplexacion
1. entrar como su
2. mkdir -p /u02/instancia/orcl
3. entrar a sqlplus como sysdba
4. sqlplus / as sysdba
5. shutdown immediate
6. create pfile from spfile;
7. cd /u01/app/oracle/product/11.2.0/db_1/dbs
8. nano /u01/app/oracle/product/11.2.0/db_1/dbs/initorcl.ora
9. Agregar linea en Control Files '/u02/instancia/orcl/control03.ctl'
10. Sobreescribir initorcl.ora
11. Entrar como superadministrador
12. su 
13. cp /u01/app/oracle/oradata/orcl/control01.ctl /u02/instancia/orcl/control03.ctl 



- Configurar copia de la BD
- - Configurar Politicas de retencion
- 
