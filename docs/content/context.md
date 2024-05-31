# Contexto

## Ciencia de Datos

> Ciencia de Datos es el estudio de extraer valor de los datos. Valor que puede ser en forma de insights (nuevas perspectivas) o conclusiones.

*[Data Science in Context: Foundations, Challenges, Opportunities.](https://datascienceincontext.com/)*

![piramide](../assets/images/piramidePNG.PNG){ width="600" }

*[The AI Hierarchy of Needs (Mónica Rogati, Hackernoon)​](https://hackernoon.com/the-ai-hierarchy-of-needs-18f111fcc007)*

> La triste realidad es que la mayoría de los proyectos de IA fracasan. Según una investigación de Gartner, solo el 15% de las soluciones de IA implementadas para 2022 serán exitosas, y serán muchas menos las que crearán un valor positivo en términos de ROI.

*[Why most AI implementations fail, and what enterprises can do to beat the odds​.](https://venturebeat.com/ai/why-most-ai-implementations-fail-and-what-enterprises-can-do-to-beat-the-odds/)*

![mlops](../assets/images/mlops.PNG){ width="600" }

*[MLOps: Why you Might Want to use Machine Learning](https://ml-ops.org/content/motivation)*

## Principios

Es deseable tener una buena estrategia para desarrollar experimentos computacionales.[^1]

[^1]: Noble WS (2009) A Quick Guide to Organizing Computational Biology Projects. PLOS Computational Biology 5(7): e1000424. https://doi.org/10.1371/journal.pcbi.1000424

- El principio rector fundamental es simple: **Alguien que no esté familiarizado con tu proyecto debería poder mirar los archivos de tu computadora y entender en detalle lo que hiciste y por qué**. Este "alguien" podría ser cualquiera de una variedad de personas: alguien que leyó tu artículo publicado y quiere intentar reproducir tu trabajo, un colaborador que quiere entender los detalles de tus experimentos, un futuro estudiante que trabaje en tu laboratorio y quiera ampliar tu trabajo después de que te hayas trasladado a un nuevo empleo, tu asesor de investigación, que podría estar interesado en entender tu trabajo o que podría estar evaluando tus habilidades de investigación. Sin embargo, **lo más común es que ese "alguien" seas tú**. Dentro de unos meses, puede que no recuerdes en qué estabas trabajando cuando creaste un conjunto particular de archivos, o puede que no recuerdes las conclusiones que sacaste. Tendrás que pasar tiempo reconstruyendo tus experimentos anteriores o perder las ideas que obtuviste de esos experimentos.

- Esto nos lleva al segundo principio, que en realidad es más como una versión de la Ley de Murphy: **Todo lo que hagas, probablemente tendrás que hacerlo de nuevo**. Inevitablemente, descubrirás algún defecto en tu preparación inicial de los datos que se están analizando, obtendrás acceso a nuevos datos o decidirás que la parametrización de un modelo particular no era lo suficientemente amplia. Esto significa que el experimento que hiciste la semana pasada, o incluso el conjunto de experimentos en los que has estado trabajando durante el último mes, probablemente necesitarán ser repetidos. Si has organizado y documentado tu trabajo claramente, repetir el experimento con los nuevos datos o la nueva parametrización será mucho, mucho más fácil.