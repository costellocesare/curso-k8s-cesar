# Creando el frontend básico en HTML/CSS

## Objetivo
Construir una interfaz sencilla para interactuar con la API de notas.

## Código base (`index.html`)
```html
<!DOCTYPE html>
<html>
<head>
    <title>Notas App</title>
</head>
<body>
    <h1>Notas</h1>
    <form id="notaForm">
        <input type="text" id="notaInput" placeholder="Escribe una nota..." required>
        <button type="submit">Agregar nota</button>
    </form>
    <ul id="listaNotas"></ul>
    <script>
        async function cargarNotas() {
            const res = await fetch('/notas');
            const notas = await res.json();
            const lista = document.getElementById('listaNotas');
            lista.innerHTML = '';
            notas.forEach((nota, idx) => {
                const li = document.createElement('li');
                li.textContent = nota.texto || JSON.stringify(nota);
                const btn = document.createElement('button');
                btn.textContent = 'Eliminar';
                btn.onclick = () => borrarNota(idx);
                li.appendChild(btn);
                lista.appendChild(li);
            });
        }

        async function agregarNota(e) {
            e.preventDefault();
            const texto = document.getElementById('notaInput').value;
            await fetch('/notas', {
                method: 'POST',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify({ texto })
            });
            document.getElementById('notaInput').value = '';
            cargarNotas();
        }

        async function borrarNota(idx) {
            await fetch('/notas/' + idx, { method: 'DELETE' });
            cargarNotas();
        }

        document.getElementById('notaForm').addEventListener('submit', agregarNota);
        cargarNotas();
    </script>
</body>
</html>
```

## Ejercicio
- Abre este archivo en tu navegador y prueba agregar y eliminar notas.
- Modifica el estilo con CSS a tu gusto.

---
[Volver al índice](../../README.md)