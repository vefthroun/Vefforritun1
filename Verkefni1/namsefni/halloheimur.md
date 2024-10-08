### Uppsetning á Flask með VENV 
[Flask tutorial in VS Code](https://code.visualstudio.com/docs/python/tutorial-flask).

Ef þú færð eftirfarandi skilaboð í Windows:

```
C:\vef31> venv\scripts\activate
venv\scripts\activate : File C:\vef31\venv\scripts\Activate.ps1 cannot be loaded because running scripts is disabled
on this system. For more information, see about_Execution_Policies at https:/go.microsoft.com/fwlink/?LinkID=135170. 
```
**Lausn:** Í powershell (run as admin)
`set-executionpolicy remotesigned`

---

### Halló heimur 
 
```python
# import Flask class in Python
from flask import Flask

# Create app, that hosts the application. Don't worry about that __name__ object, it's just a convention.
app = Flask(__name__)

# route() maps what you type in the browser (the url) to a Python function.
# @app.route() (@ er decorator í python) bindur fallið index() við URL. 
# Whenever a browser requests a URL, the associated function is called and the return value is sent back to the browser
@app.route('/')
def index():
    # fallið skilar hér streng sem er sendur til biðlara (e. client) í vafra.
    return "<h1>Hello, World!</h1>"  # Við getum blandað html og texta.

# This starts the web app 
if __name__ == '__main__':
    # run, starts a built-in development server
    app.run(debug=True, use_reloader=True)   
            # debug=True. debug er nytsamlegt í vefþróun, gefur skýrari villuskilaboð.
            # use_reloader. use_reloader=True þýðir að þú þarft ekki að endurkeyra python skrá stöðugt þegar þú gerir kóðabreytingar. 
     
# Keyrðu python skránna í terminal og skoðaðu url í vafra (localhost), en með Flask kemur web server sem vð getum notað
```

#### Nánari skýringar

- Decorators[`@app.route('/')`](decorators.md) 
- Flask API documentation [`Flask(__name__)`](https://flask.palletsprojects.com/en/2.2.x/api/#flask.Flask)
- Python documentation [`__main__`](https://docs.python.org/3/library/__main__.html)
- Stack Overflow [`if __name__ == '__main__':`](https://stackoverflow.com/questions/419163/what-does-if-name-main-do)
- [Quick Start](https://flask.palletsprojects.com/en/2.3.x/quickstart/)
- [Hello Tiny Flask App](http://www.compjour.org/lessons/flask-single-page/hello-tiny-flask-app/)
<!--
#### Ef við viljum sleppa `app.run` í kóðanum

- Stillum umhverfisbreytu í terminal: `$env:FLASK_APP = "app.py"`
- Keyrum app í terminal: `flask run` 

-->
