# wrapper to mysql-connector

- close and open connection `@name_task` -> your def
- **connected()** return connection in `MySQL`
- **get_cursor()** return instance of `cursor`
- **desconected()** return bool for `connection` sucess or fail
- ClassConnection() -> `constructor` of `MySQLConnector`

## EXAMPLE:

```
from wrapper import ClassConnectionparams = {
'host':'your_host',
'user':'your_user',
'password':'your_password',
'port':3306,
}
params = {
'host':'your_host',
'user':'your_user',
'password':'your_password',
'port':3306,
}
cls = ClassConnection(\*\*params)
conn = cls.connected()
cur = cls.get_cursor()cur.execute('your_operation_sql')
conn.commit()
```


## EXAMPLE 2:

```
from wrapper import ClassConnectionparams = {
    'host':'your_host',
    'user':'your_user',
    'password':'your_password',
    'port':3306,
}cls = ClassConnection(\*\*params)
conn = cls.connected()
cur = cls.get_cursor()@cls.query
def select_all(table)
    cur.execute(f'select \* from {table}') # autoclosing cursor and connection@cls.update
def update(table,column,value,id)
    cur.execute(f'update {table} set {column} = {value} where id = {id}')  # autoclosing cursor and connection and autocommit
```
