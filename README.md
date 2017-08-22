# python-flask-mysql
This is just a simple demo how to develop a webservice using python, flask and mysql. ``pymysql`` python mysql driver is used here.

```
$ python -V
Python 3.6.0 
```

### Install required python packages

```
   $ pip install -r requirements.txt
```

### Config and start webservice

##### Configure MySQL settings

In ``config.py`` file, fill in your real MySQL connection settings

```
_DB_CONF = {
 'host':'<YOUR-MYSQL-HOST>',
 'port':3306,
 'user':'<YOUR-MYSQL-USERNAME>',
 'passwd':'<YOUR-MYSQL-PASSWORD>',
 'db':'<YOUR-MYSQL-DATABASE>'
}
```

##### Change MySQL query

In ``main.py`` file, put your real mysql select query here

```
    sql="<PUT YOUR MySQL QUERY HERE>"
```


##### Start Webservoce

```
   $ gunicorn -b :8080 main:app
```

### Test your webservice using curl

```
   curl http://localhost:8080/test
```

You can also test your webservice remotely

```
   curl http://<SERVER-IP>:8080/test
```

If you have trouble with 'Access-Control-Allow-Origin' error when making cross-origin ajax call,  add the following

```
from flask_cors import CORS

app = Flask(__name__)

"""
CORS function is to avoid No 'Access-Control-Allow-Origin' error
"""
CORS(app)
```

