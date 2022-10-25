# Python x ODBC
ODBC est un middleware (manager de drivers) qui permet d'établir une connexion avec un serveur de base de données et d'y communiquer avec.

## Mini doc
Avant tout installer la package pyodbc.
``` py
    import pyodbc
```

### Vérifier les drivers disponible
``` python
    print(pyodbc.drivers())
```

### Etablir une connexion avec le driver MySQL
``` python
    cnxn = pyodbc.connect(
        'DRIVER=MySQL ODBC 8.0 ANSI Driver;'
        'SERVER=localhost;'
        'DATABASE=test;'
        'UID=root;'
        'PWD=;'
        'charset=utf8mb4;'
    )
```

### Instancier un curseur d'execution
``` python 
    cursor = cnxn.cursor()
```

### Executer un query sql. But -> récuperer les bases de données
``` python
    query = 'show databases'
    cursor.execute(query)
    result = cursor.fetchAll()
    print(result)
```

## Sources
https://docs.devart.com/odbc/mysql/python.htm
https://github.com/mkleehammer/pyodbc
