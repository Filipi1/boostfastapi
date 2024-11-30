# Boostfastapi - Documentation

For full documentation visit [mkdocs.org](https://www.mkdocs.org).

## Integrando com o projeto

### Configurando

Para que tudo funcione corretamente, você deve adicionar o código:

```python
app = FastAPI()
BoostAPI.initialize(app)
```

#### (Opcional)
Você pode adicionar o parâmetro "default_prefix" para definir um prefix global para sua aplicação.

```python
app = FastAPI()
BoostAPI.initialize(app, default_prefix="api")
```

Desta forma, todas as rotas da sua aplicação terão como prefixo "api", por exemplo:

http://localhost:3000/api/...

E é apenas isso! 🚀

## Criando Controllers

Para criar uma controller, você precisará decorar sua classe com o decorador [@BoostAPI.Controller] como no exemplo abaixo:

```python
@BoostAPI.controller(name="Awesome", tag="MyGroupName", version="v2")
class MyAwesomeController(Controller):
    ...
```

A controller para "Awesome" será criada automáticamente, e o resultado ficará algo como:

http://localhost:3000/api/v2/awesome/...

## Criando Rotas

```python
@BoostAPI.controller(name="Awesome", tag="MyGroupName", version="v2")
class MyAwesomeController(Controller):
    @BoostAPI.route("element/{id}", method="GET")
    def my_function(self, id: int):
        ...
```


* `@BoostAPI.controllers [dir-name]` - Marks a Controller


* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.

## Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.
