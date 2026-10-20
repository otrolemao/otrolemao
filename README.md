# EJEMPLO SIMPLIFICADO DE GENERADOR (No es el original, pero sirve para entender)

# 1. CONFIGURACIÓN DE COLORES (Cámbialos a tu gusto)
COLOR_FONDO = "#0d1117"  # Fondo oscuro tipo terminal
COLOR_TEXTO = "#c9d1d9"  # Texto gris claro
COLOR_VERDE = "#39d353"  # Verde de GitHub para los "OK"

# 2. TUS DATOS (Edita esta sección)
DATOS = {
    "usuario": "tu_usuario",
    "status": "Running (stable)",
    "os": "Tu Sistema Operativo",
    "uptime": "Tus años/meses programando",
    "lenguajes": "Python, JS, SQL...",
    "hobbies": "Tus hobbies",
    "contacto": "tu@email.com"
}

# 3. GENERACIÓN DEL TEXTO (El formato "neofetch")
# Aquí se crean las líneas con los puntos suspensivos
lineas_texto = []
for clave, valor in DATOS.items():
    # Esto crea algo como: ". Status: ......... Running"
    puntos = "." * (30 - len(clave) - len(valor)) 
    linea = f". {clave}: {puntos} {valor}"
    lineas_texto.append(linea)

# 4. EL SVG (Aquí se dibuja todo)
# En el original, aquí se inserta el bloque de texto ASCII de tu foto a la izquierda
# y las lineas_texto a la derecha.

svg = f'''
<svg width="800" height="400" xmlns="http://www.w3.org/2000/svg">
  <!-- Fondo -->
  <rect width="100%" height="100%" fill="{COLOR_FONDO}" rx="10"/>
  
  <!-- Aquí iría tu foto en ASCII (izquierda) -->
  <text x="20" y="50" fill="{COLOR_TEXTO}" font-family="monospace">
     [ TU FOTO EN ASCII SE GENERA AQUÍ ]
  </text>

  <!-- Texto de datos (derecha) -->
  <text x="400" y="50" fill="{COLOR_TEXTO}" font-family="monospace">
     {chr(10).join(lineas_texto)}
  </text>
</svg>
'''
