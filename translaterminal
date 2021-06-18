# Importando las librerías necesarias
import requests, os
import pyperclip as clipboard

# Estableciendo valores de variables y constantes

LOGO = """
 _____                     _      _____                    _             _ 
/__   \_ __ __ _ _ __  ___| | __ /__   \___ _ __ _ __ ___ (_)_ __   __ _| |
  / /\/ '__/ _` | '_ \/ __| |/ _` |/ /\/ _ \ '__| '_ ` _ \| | '_ \ / _` | |
 / /  | | | (_| | | | \__ \ | (_| / / |  __/ |  | | | | | | | | | | (_| | |
 \/   |_|  \__,_|_| |_|___/_|\__,_\/   \___|_|  |_| |_| |_|_|_| |_|\__,_|_|
                                                                           
"""

INFORMACION = """[info] \t\tSoftware de traducción de idiomas por terminal.
[created by] \tLuis Alejandro Salcedo (https://github.com/LuisAlejandroSalcedo)
[edited by] \t__Rodion__ (https://github.com/RodionButEncapsulated) """

LENGUAJES = """
Idiomas Frecuentes:

[es] Español    \t[en] Inglés
[ru] Ruso       \t[de] Alemán
[fr] Francés    \t[it] Italiano
[co] Coreano    \t[ja] Japonés
[pt] Portuges   \t[exit] Salir

"""

# Creando la función de petición de traducción
def Traduccion(source, target, text):
	parametros = {'sl': source, 'tl': target, 'q': text}
	cabeceras = {"Charset":"UTF-8","User-Agent":"AndroidTranslate/5.3.0.RC02.130475354-53000263 5.1 phone TRANSLATE_OPM5_TEST_1"}
	url = "https://translate.google.com/translate_a/single?client=at&dt=t&dt=ld&dt=qca&dt=rm&dt=bd&dj=1&hl=es-ES&ie=UTF-8&oe=UTF-8&inputm=2&otf=2&iid=1dd3b944-fa62-4b55-b330-74909a99969e"
	response = requests.post(url, data=parametros, headers=cabeceras)
	if response.status_code == 200:
		for x in response.json()['sentences']:
			return x['trans']
	else:
		return "Ocurrió un error"    

# Creando la función principal
def app():
    while True:
        os.system("clear")
        print(LOGO)
        print(INFORMACION)
        print(LENGUAJES)

        language_to = input("[?] A qué idioma deseas traducir la frase: ")

        if language_to == "exit":
            break
        else:
            text = input("[+] Ingrese un texto para traducir: ")

            if text == "exit":
                break
            else:
                respuesta = Traduccion("es", language_to, text)
                clipboard.copy(respuesta)
                respuesta = ("[Resultado] " + str(respuesta) + " (Copiado al portapapeles)")
                input(respuesta)
                os.system("clear")

# Llamando a la función principal
app()
