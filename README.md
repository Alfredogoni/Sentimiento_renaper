# Sentimiento_renaper
Análisis de sentimiento de los tweets que mencionen la palabra Renaper


# La diciplina

El procesamiento del lenguaje natural (NLP) es una rama de la inteligencia artificial que ayuda a las computadoras a entender, interpretar y manipular el lenguaje humano. NLP toma elementos prestados de muchas disciplinas, incluyendo la ciencia de la computación y la lingüística computacional, en su afán por cerrar la brecha entre la comunicación humana y el entendimiento de las computadoras. El procesamiento del lenguaje natural ayuda a las máquinas a comunicarse con humanos en su lenguaje y escala otras tareas relacionadas con el mismo.
Por ejemplo, NLP hace posible que las computadoras lean texto, escuchen una voz y la interpreten, midan el sentimiento y determinen qué partes son importantes.
Como sabemos, el lenguaje es sumamente complejo y diverso. Nos expresamos de maneras infinitas tanto en forma oral como escrita. En términos generales, las tareas NLP dividen el lenguaje en piezas elementales más cortas, intentan entender las relaciones entre las piezas y exploran cómo funcionan juntas para crear un significado. El análisis de sentimientos también conocido como minería de opinión (opinion mining), es el estudio sistemático que interpreta las actitudes, opiniones y sentimiento del usuario hacia una marca/cuenta/persona. Específicamente, el análisis de sentimiento consiste en determinar el tono emocional que hay detrás de una serie de palabras y clasificarlas como positiva, negativa o neutra.
Si bien todo es analizable, no se puede confiar en su totalidad dicha interpretación por lo ya mencionado anteiormente, hay tantas expresiones y lenguajes como personas, y de ahí su subjetividad. El análisis de sentimiento no es entonces, por el momento, 100% preciso. De hecho, en función del contexto, las cifras de acierto pueden andar docenas de puntos por debajo de la perfección (60/80%).
Los motivos más usuales son: Ni siquiera los seres humanos somos capaces de estar 100% de acuerdo sobre la “intensidad de la polaridad” (cuanto más cerca está de una certeza en la clasificación) de la mayoría de las frases. Si se pide a varias personas que analicen el sentimiento de un conjunto de frases, en la mayoría de las frases no van a coincidir más de cuatro personas.

# Para hacer esto realizaremos:

- Descargar tweets mencionando el termino de los últimos 15 días que contengan la palabra “renaper”, lógicamente, también va a estar incluida “renaper_ar”. Para eso usaremos la herramienta Tweepy.
- Preprocesaremos las palabras para evitar errores: quitaremos tildes, mayúsculas y signos de puntuación.
- Procesaremos en AWS para conseguir la categorización de los términos y la polaridad.

Ejemplo POSITIVO

Que linda estuvo la fiesta!

    Neutral 0.01 confidence / Positive 0.98 confidence / Negative 0.00 confidence / Mixed 0.00 confidence

Ejemplo NEGATIVO

Estoy preocupado por esa situación

    Neutral 0.27 confidence / Positive 0.02 confidence / Negative 0.70 confidence / Mixed 0.00 confidence

Ejemplo NEUTRAL

    La Dirección Nacional de Población tiene como propósito diseñar, elaborar y evaluar las políticas de población y migraciones, como asimismo, la formulación de programas que las implementen. La diversidad de las acciones y el carácter multisectorial de las mismas, requiere un marco de complementación y colaboración con distintos organismos del Estado, Organizaciones no Gubernamentales y Organismos Internacionales con incumbencia en la temática poblacional.

    Neutral 0.96 confidence / Positive 0.03 confidence / Negative 0.00 confidence / Mixed 0.00 confidence

Ejemplo MIX (de un mail del Banco)

    A la promo que ya conoces le sumamos cuatro días más, del jueves 24 al lunes 28 de septiembre disfrutá comprando en Mercado Libre.

    Neutral 0.54 confidence / Positive 0.45 confidence / Negative 0.00 confidence / Mixed 0.00 confidence

Dividimos los tweets y los autores en relación a la categorización para poder evaluar las palabras, y la frecuencia de ocurrencia de ellas, para poder intentar analizar las inquietudes de los usuarios, logrando obtener listas de palabras más repetidas para cada una de las categorías y cuáles fueron los usuarios que más escribieron en cada una.

