# POSTGRES COMMANDS
## Backup And Restore:

Backup:  `pg_dump -U {user-name} {source_db} -f {dumpfilename.sql} --format=c|d|p`
Restore: `psql -U {user-name} -d {desintation_db}-f {dumpfilename.sql}`
Both accepts: -h host -p port -U user -d dbname

`pg_restore -d db dbdumpfile -j jobs`
`psql db < file.dump` # using default dump format (sql text):


## Metadata: 
hostname: `select inet_server_addr()`
port: `select setting from pg_settings where name = 'port'`
list schemas: `select nspname from pg_catalog.pg_namespace;`

copy (select * from dbname) TO '<file_location>/file_name' DELIMITER ',' CSV HEADER;

## References: 

[Backup]: http://www.postgresql.org/docs/8.1/static/backup.html
[Sql Copy]: http://www.postgresql.org/docs/current/static/sql-copy.html
