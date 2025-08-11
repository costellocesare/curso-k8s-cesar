# Creando una API sencilla de notas (backend)

## Objetivo
Desarrollar una API básica con Flask para gestionar notas (crear, ver y eliminar).

## Código base (`app.py`)
```python
from flask import Flask, request, jsonify

app = Flask(__name__)
notas = []

@app.route('/notas', methods=['GET'])
def obtener_notas():
    return jsonify(notas)

@app.route('/notas', methods=['POST'])
def agregar_nota():
    data = request.get_json()
    notas.append(data)
    return jsonify({'msg': 'Nota agregada'}), 201

@app.route('/notas/<int:nota_id>', methods=['DELETE'])
def borrar_nota(nota_id):
    if 0 <= nota_id < len(notas):
        notas.pop(nota_id)
        return jsonify({'msg': 'Nota eliminada'})
    return jsonify({'error': 'Nota no encontrada'}), 404

if __name__ == '__main__':
    app.run(debug=True)
```

## Ejercicio
- Prueba la API con [Postman](https://www.postman.com/) o [curl](https://curl.se/).
- Agrega, consulta y elimina notas.

## Reto
- Agrega una ruta para modificar una nota existente (HTTP PUT o PATCH).

---
[Volver al índice](../../README.md)