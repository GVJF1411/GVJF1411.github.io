# GVJF1411.github.io
Pasar Tareas
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Subir y descargar archivos</title>
    <style>
        body {
            font-family: "Times New Roman", Times, serif;
            background-color: #f2f2f2;
            margin: 0;
            padding: 0;
        }

        h1 {
            color: #1877F2;
            text-align: center;
            padding: 20px;
        }

        .container {
            max-width: 600px;
            margin: 20px auto;
            background-color: #fff;
            padding: 20px;
            border-radius: 5px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }

        .file-upload {
            margin-bottom: 20px;
        }

        .file-upload input[type="file"] {
            display: none;
        }

        .file-upload label {
            display: block;
            background-color: #1877F2;
            color: #fff;
            padding: 10px 20px;
            border-radius: 5px;
            cursor: pointer;
            text-align: center;
            transition: background-color 0.3s;
        }

        .file-upload label:hover {
            background-color: #0F5599;
        }

        .file-list {
            list-style-type: none;
            padding: 0;
        }

        .file-list li {
            margin-bottom: 10px;
        }

        .file-list a {
            color: #1877F2;
            text-decoration: none;
            margin-right: 10px;
        }

        .file-list a:hover {
            text-decoration: underline;
        }
    </style>
</head>
<body>
    <h1>Subir y descargar archivos</h1>

    <div class="container">
        <div class="file-upload">
            <input type="file" name="file" id="file" multiple>
            <label for="file">Seleccionar archivos</label>
        </div>

        <ul class="file-list">
            <!-- Aquí se mostrarán los archivos subidos -->
        </ul>
    </div>

    <script>
        // Función para mostrar el nombre de los archivos seleccionados
        document.getElementById("file").addEventListener("change", function (event) {
            var fileList = event.target.files;
            var fileNames = [];

            for (var i = 0; i < fileList.length; i++) {
                fileNames.push(fileList[i].name);
            }

            var fileContainer = document.querySelector(".file-list");
            fileContainer.innerHTML = "";

            fileNames.forEach(function (fileName) {
                var listItem = document.createElement("li");
                var link = document.createElement("a");
                link.href = "#"; // Agrega aquí la URL de descarga del archivo
                link.textContent = fileName;

                listItem.appendChild(link);
                fileContainer.appendChild(listItem);
            });
        });
    </script>
</body>
</html>
