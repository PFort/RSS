# Desplegar l'Aplicatiu

Aquest document explica com desplegar l'aplicatiu, incloent la configuració de l'entorn virtual, com iniciar l'aplicació i com utilitzar els modes remot i local.

## Configuració de l'Entorn Virtual

1. Navega fins al directori de l'aplicació on es troba `app.py`.

2. Crea un entorn virtual:
    - A Windows:
        ```python -m venv env```
    - A Linux:
        ```python3 -m venv env```

3. Activa l'entorn virtual:
    - A Windows:
        ```.venv\Scripts\activate```
    - A Linux:
        ```source .venv/bin/activate```
4. Ara ja pots instal·lar els paquets que necessitem:
    - Flask:
        ```pip install flask```
    - Feedparser:
        ```pip install feedparser```

## Iniciar l'Aplicació

1. Assegura't que l'entorn virtual està activat (consulta els passos anteriors).

2. Executa l'aplicació:
    ```flask run --debug```

3. L'aplicació estarà disponible a `http://127.0.0.1:5000/`.

## Iniciar l'Aplicació

Per aturar el servidor flask, fes CTRL + C al terminal integrat.

## Modes de Funcionament

L'aplicació pot funcionar en dos modes: remot i local.

### Mode Remot

En aquest mode, l'aplicació utilitza l'RSS directament de la web de La Vanguardia o El Punt Avui.

1. Per agafar les dades de l'RSS utilitzarem feedparser, utlitzarem el link de la pàgina web de La Vanguiardia o qualsevol altre pàgina de noticies y segons la secció qwue volem modificarem el link, per exemple: ```http://www.elpuntavui.cat/{seccio}.feed?type=rss```
2. Després, al document html, printarem la informació que nosaltre volguem.

### Mode Local

En aquest mode, l'aplicació utilitza un fitxer XML descarregat.

1. Descarrega l'XML de la web de La Vanguardia o el diari que nosaltrs volguem.

2. Guarda el fitxer XML en el mateix directori que `app.py`.

3. Modifica el codi a `app.py` per utilitzar el fitxer XML local en lloc de l'XML remot. Assegura't que el camí al fitxer XML és correcte. En comptes de posar el link, posarem la ruta de l'XML: ```xml = f"./rss/elpuntavui/{seccio}.xml"```
