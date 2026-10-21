# 20. Estado de la especificación

Volver al índice [aquí](../README.md#índice-1).

## Alcance de la especificación

## Origen y propósito

Esta especificación define la identidad visual base del frontend de `sitio`.

La especificación fue derivada de las decisiones de diseño tomadas durante la definición visual del proyecto y de las representaciones finales aprobadas para los temas claro y oscuro.

Su objetivo es servir como referencia técnica durante la implementación con Angular y Tailwind CSS y durante las etapas posteriores de accesibilidad e implementación.

Los valores contenidos aquí deben considerarse la base concreta de implementación.

Los ajustes posteriores deben responder a una necesidad real detectada durante el desarrollo, no a una reinterpretación arbitraria de la identidad visual.

---

## Decisiones consolidadas

Los siguientes elementos de identidad visual quedan definidos:

1. tipografía concreta;
2. escala tipográfica relativa de escritorio;
3. escala tipográfica relativa de pantallas estrechas;
4. puntos de ruptura tipográficos;
5. alturas de línea;
6. pesos tipográficos;
7. paleta del tema claro;
8. paleta del tema oscuro;
9. estados visuales;
10. sombras;
11. bordes;
12. escala de espaciado;
13. adaptación del padding general;
14. proporciones del layout de escritorio amplio;
15. composición de escritorio intermedio;
16. composición de pantallas estrechas;
17. punto de ruptura natural de Inicio;
18. cabecera expandida y compacta de escritorio;
19. adaptación de cabecera en pantallas estrechas;
20. navegación lateral de escritorio;
21. navegación móvil;
22. apertura y cierre del menú móvil;
23. apertura y cierre de grupos expandibles;
24. restablecimiento de grupos después de la navegación;
25. permanencia de navegación y controles durante el desplazamiento;
26. foto y composición de cabecera;
27. biblioteca, mapeo, tamaños y uso de iconos;
28. mapeo de controles globales;
29. mapeo de navegación;
30. mapeo de tipos de contenido y acciones;
31. mapeo de iconos de Sobre mí;
32. mapeo de iconos de Contactos;
33. estructura visual de Inicio;
34. representación de contenido destacado;
35. área de exposición y actualizaciones;
36. reorganización de Actualizaciones en escritorio intermedio;
37. composición vertical de Inicio en pantallas estrechas;
38. estructura general de las páginas internas;
39. región variable de Contenido;
40. adaptación de componentes internos según espacio disponible;
41. reglas para contenido interno ancho;
42. composición visual de Sobre mí;
43. adaptación responsive de Sobre mí;
44. composición visual de Contactos;
45. formulario de contacto;
46. adaptación responsive del formulario;
47. lenguaje visual común de tarjetas;
48. rejillas adaptables de listados;
49. representación de certificados;
50. representación de certificaciones;
51. adaptación responsive de Certificado y Certificación;
52. listado y detalle de Proyectos;
53. representación del lenguaje principal de los proyectos;
54. adaptación responsive del detalle de Proyecto;
55. listado y detalle de Artículos;
56. representación de fechas de Artículos;
57. representación de contenido Markdown;
58. adaptación responsive de Artículos;
59. equivalencia estructural y de contenido entre los temas claro y oscuro;
60. equivalencia responsive entre los temas claro y oscuro;
61. unidad de presentación y límites de contenido independiente;
62. representación mediante skeleton durante la carga;
63. adaptación responsive de skeletons;
64. comportamiento de estados vacíos;
65. comportamiento de errores de carga;
66. tratamiento de elementos visuales obligatorios fallidos;
67. estados de carga y error de elementos subordinados de navegación;
68. estados de carga y error de cabecera;
69. representación de páginas y elementos no encontrados;
70. estado de envío en curso del formulario;
71. confirmación de envío satisfactorio;
72. representación de errores de validación;
73. comportamiento visible del honeypot;
74. representación del límite de envíos;
75. representación de fallos de envío;
76. relación entre estados y colores semánticos;
77. conservación de regiones independientes durante estados parciales;
78. conservación de contenido y jerarquía durante la adaptación responsive;
79. reorganización antes que eliminación de contenido;
80. prevención de desplazamiento horizontal de la página;
81. redimensionamiento proporcional de elementos visuales;
82. scroll horizontal limitado al componente cuando resulte necesario;
83. nivel WCAG 2.2 AA como referencia de accesibilidad;
84. coherencia entre orden visual, orden del DOM y orden de foco;
85. navegación mediante teclado y uso restringido de `tabindex`;
86. estructura semántica de cabecera, navegación y contenido principal;
87. jerarquía semántica de encabezados;
88. ausencia de movimiento automático de foco durante la carga inicial;
89. navegación estructural sin enlace adicional de salto al contenido principal;
90. semántica de los grupos expandibles;
91. comunicación mediante `aria-expanded` y relación mediante `aria-controls`;
92. exclusión del recorrido de foco de contenido oculto;
93. nombres accesibles de controles;
94. tratamiento accesible de iconos con texto e iconos sin texto;
95. asociación entre etiquetas y campos del formulario;
96. placeholders concretos del formulario;
97. representación semántica de errores de validación;
98. relación de errores mediante `aria-describedby`;
99. representación no interruptiva de confirmaciones y límites;
100. representación inmediata de fallos de envío;
101. semántica de unidades de carga mediante `aria-busy`;
102. exclusión accesible de las formas visuales del skeleton;
103. clasificación funcional de imágenes;
104. tratamiento de imágenes decorativas, informativas, funcionales, complejas y de texto;
105. alternativa textual localizada de la fotografía personal;
106. localización de textos relacionados con accesibilidad;
107. método y umbrales de cálculo de contraste;
108. paleta accesible definitiva del tema claro;
109. garantía de contraste de los usos permitidos del tema claro;
110. auditoría AA y AAA de la paleta clara;
111. token único de borde accesible del tema claro;
112. indicador de foco del tema claro;
113. comunicación de estados sin dependencia exclusiva del color;
114. identificación estructural y visual de enlaces;
115. comprobación de colores efectivos después de composiciones visuales;
116. actualización localizada del título del documento;
117. composición del título mediante información específica y nombre localizado del sitio;
118. localización de la representación del nombre personal dentro del título;
119. paleta accesible definitiva del tema oscuro;
120. garantía de contraste de todos los usos permitidos del tema oscuro;
121. separación entre rojo de primer plano y rojo de fondo en el tema oscuro;
122. auditoría AA y AAA de la paleta oscura;
123. borde funcional accesible del tema oscuro;
124. separador decorativo independiente del borde funcional;
125. indicador de foco accesible del tema oscuro;
126. estados semánticos accesibles del tema oscuro;
127. enlaces normales, hover y visitados accesibles del tema oscuro;
128. contraste de botones principales en estado normal y hover del tema oscuro;
129. contraste de botones secundarios del tema oscuro;
130. contraste del placeholder del tema oscuro;
131. contraste de texto principal, secundario y tenue sobre las superficies permitidas del tema oscuro;
132. garantía de contraste sobre fondos semánticos del tema oscuro;
133. capa mínima de contraste de la cabecera del tema oscuro;
134. garantía de contraste de la cabecera frente al caso de máxima luminosidad de la fotografía;
135. conservación de la capa mínima detrás de toda la región textual de la cabecera;
136. independencia entre la garantía de contraste de la cabecera y la fotografía concreta utilizada;
137. distinción entre carga inicial y cambio interno de página para la gestión de foco;
138. ausencia de movimiento programático de foco durante la carga inicial;
139. foco programático en el encabezado principal después de una navegación interna hacia una nueva página;
140. uso de `tabindex="-1"` en el encabezado principal para permitir foco programático sin cambiar el recorrido normal mediante teclado;
141. conservación de `main` como región semántica sin convertirla en destino automático de foco;
142. conservación del foco durante actualizaciones que permanecen dentro de la misma página;
143. tratamiento de las páginas de contenido no encontrado como destinos completos de navegación;
144. cierre del menú de navegación estrecho antes de trasladar el foco al encabezado principal de la nueva página;
145. comunicación del cambio de contexto mediante el título del documento y el encabezado principal sin una región `aria-live` adicional;
146. estado ocupado del formulario durante el envío mediante `aria-busy`;
147. estado temporal de solo lectura de los campos mediante `readonly`;
148. conservación de los campos en el recorrido de foco durante el envío;
149. indisponibilidad semántica temporal del botón mediante `aria-disabled`;
150. conservación del botón de envío en el recorrido de foco;
151. bloqueo funcional de cualquier segundo envío mientras existe una solicitud pendiente;
152. anuncio no interruptivo de `enviando...` mediante `role="status"`;
153. ubicación de la región de progreso fuera del formulario marcado como ocupado;
154. conservación del foco en el control desde el que se inició el envío;
155. restauración de los estados semánticos del formulario antes de comunicar el resultado final;
156. ausencia de un anuncio adicional de finalización cuando el resultado ya comunica el desenlace;
157. presencia obligatoria de `src` y `alt` en todas las imágenes de contenido;
158. utilización de una cadena textual o una cadena vacía como valor de `alt`, sin utilizar `null`;
159. responsabilidad de `sitio-api` sobre la determinación del valor final de `alt` según la función y el contexto de la imagen;
160. representación directa de `alt` por `sitio` sin generación, sustitución, vaciado ni reclasificación por parte del frontend;
161. posibilidad de utilizar un mismo elemento visual con alternativas distintas cuando cambia su función entre representaciones;
162. tratamiento informativo o funcional de las imágenes de `Sobre mí` según su función editorial;
163. alternativa vacía para las imágenes de proyectos utilizadas en representaciones resumidas;
164. alternativa informativa para la imagen principal de un proyecto en su detalle;
165. alternativa vacía para las imágenes principales de artículos utilizadas en representaciones resumidas;
166. determinación editorial de la alternativa de la imagen principal de un artículo en su detalle;
167. clasificación individual de las imágenes incluidas dentro del contenido Markdown;
168. alternativa vacía para las imágenes de certificados y certificaciones utilizadas en representaciones resumidas;
169. alternativa informativa para las imágenes de certificados y certificaciones en sus páginas de detalle;
170. disposición de información extensa de documentos mediante contenido textual accesible en lugar de concentrarla únicamente en `alt`;
171. utilización exclusiva de iconos como representación visual de los medios de Contactos;
172. exclusión de imágenes de contenido de las tarjetas de Contactos;
173. utilización de `3.1.1 Idioma de la página`, nivel A, para la declaración del idioma principal al no existir un criterio AA equivalente para esa exigencia;
174. utilización de `3.1.2 Idioma de las partes`, nivel AA, para las partes cuyo idioma difiere del idioma principal;
175. ausencia de un criterio AAA adicional específico para la declaración semántica mediante `lang`;
176. utilización de etiquetas BCP 47 válidas en las declaraciones lingüísticas;
177. declaración del idioma activo del sistema como idioma principal del documento;
178. actualización del idioma principal del documento después de una selección manual de idioma;
179. conservación del idioma principal durante la navegación interna que mantiene el mismo idioma activo;
180. conservación del idioma del documento cuando una unidad utiliza un idioma de respaldo;
181. declaración del idioma real de las variantes presentadas mediante respaldo;
182. aplicación de la declaración lingüística solamente a la región correspondiente al contenido que utiliza ese idioma;
183. conservación del idioma activo del sistema en los textos propios de la interfaz y en el aviso de utilización de un idioma de respaldo;
184. declaración independiente del idioma de cada unidad dentro de colecciones que presentan variantes en idiomas diferentes;
185. separación semántica entre contenido localizado y acciones de interfaz cuando utilizan idiomas diferentes dentro del mismo componente;
186. utilización del idioma real de la variante en sus encabezados y alternativas textuales;
187. conservación del idioma semántico del encabezado principal cuando recibe foco programático;
188. declaración de cambios lingüísticos internos en el elemento semántico correspondiente;
189. aplicación de las excepciones establecidas por WCAG para nombres propios, términos técnicos, idiomas indeterminados y expresiones incorporadas al idioma circundante;
190. conservación de los cambios lingüísticos editoriales durante el procesamiento del contenido Markdown;
191. ausencia de detección automática del idioma por análisis del texto;
192. utilización de herencia cuando el contenido mantiene el mismo idioma de su ancestro;
193. ausencia de `lang=""` cuando el idioma es conocido;
194. actualización de la declaración lingüística cuando cambia la variante representada;
195. utilización del idioma de la solicitud que produjo el contenido presentado sin añadir una propiedad general adicional al contrato para determinar el idioma de la variante;
196. implementación de la escala tipográfica mediante unidades relativas `rem`;
197. respeto al tamaño de fuente raíz configurado por el usuario mediante `font-size: 100%`;
198. equivalencia de referencia de la escala tipográfica basada en una raíz habitual de `16px` sin fijar ese valor como tamaño absoluto;
199. aplicación de la escala tipográfica a encabezados, párrafos, navegación, controles, campos, acciones, metadatos, etiquetas y textos auxiliares;
200. herencia tipográfica de los controles nativos de formulario;
201. utilización de dimensiones mínimas en los componentes textuales cuya presentación normal dispone de una altura definida;
202. crecimiento obligatorio de los contenedores cuando el texto redimensionado necesita más espacio;
203. ausencia de recorte, truncamiento, ocultación y superposición como solución al crecimiento del texto;
204. cumplimiento de `1.4.4 Redimensionamiento del texto`, nivel AA, mediante soporte hasta `200%`;
205. ausencia de restricciones sobre la ampliación normal del navegador;
206. utilización de una configuración de ventana gráfica compatible con zoom;
207. ausencia de `user-scalable=no`, `maximum-scale=1` o restricciones equivalentes;
208. reutilización de las mismas reglas responsive cuando el zoom reduce el ancho CSS disponible;
209. cumplimiento de `1.4.10 Reflujo`, nivel AA, para contenido de desplazamiento vertical hasta `320px CSS`;
210. ausencia de desplazamiento horizontal de la página para contenido normal durante el reflujo;
211. reducción natural de las rejillas hasta una tarjeta por fila cuando corresponde;
212. reorganización de los componentes horizontales cuando dejan de caber correctamente;
213. limitación del desplazamiento horizontal propio a contenido cuya estructura bidimensional necesita conservarse;
214. aplicación de la excepción de desplazamiento horizontal según la necesidad real del contenido y no según su categoría;
215. adaptación de cadenas extensas dentro de sus contenedores cuando su división conserva el significado;
216. cumplimiento de `1.4.12 Espaciado del texto`, nivel AA;
217. soporte de interlineado equivalente a `1.5` veces el tamaño de fuente sin pérdida;
218. soporte de espacio posterior a párrafos equivalente a `2` veces el tamaño de fuente sin pérdida;
219. soporte de espaciado entre letras equivalente a `0.12` veces el tamaño de fuente sin pérdida;
220. soporte de espaciado entre palabras equivalente a `0.16` veces el tamaño de fuente sin pérdida;
221. conservación del contenido y la funcionalidad cuando los valores de espaciado se aplican simultáneamente;
222. cumplimiento de `1.3.4 Orientación`, nivel AA, sin exigir una orientación concreta;
223. funcionamiento completo del sitio en orientación vertical;
224. funcionamiento completo del sitio en orientación horizontal;
225. aplicación de las reglas responsive según las dimensiones resultantes después de un cambio de orientación;
226. ausencia de bloqueo de orientación, exigencia de rotación o funciones exclusivas de una orientación;
227. ausencia de una excepción funcional que requiera orientación específica;
228. relación con `1.4.8 Presentación visual`, nivel AAA, sin declarar su cumplimiento completo únicamente por las decisiones de redimensionamiento y reflujo;
229. cumplimiento de `1.4.13 Contenido señalado con el puntero o en foco`, nivel AA, sin depender actualmente de contenido adicional activado por estos estados;
230. obligación de que cualquier contenido adicional futuro activado mediante puntero o foco sea descartable, apuntable y persistente;
231. cumplimiento de `2.5.1 Gestos del puntero`, nivel A, al no exigir gestos multipunto ni recorridos específicos para utilizar funciones propias del sitio;
232. conservación formal del nivel A de `2.5.1` al no existir un criterio AA equivalente que sustituya esa exigencia;
233. cumplimiento de `2.5.2 Cancelación del puntero`, nivel A, mediante acciones completadas por la activación normal y no por la presión inicial;
234. conservación formal del nivel A de `2.5.2` al no existir un criterio AA equivalente que sustituya esa exigencia;
235. cumplimiento de `2.5.3 Etiqueta en el nombre`, nivel A, mediante inclusión del texto visible dentro del nombre accesible;
236. conservación formal del nivel A de `2.5.3` al no existir un criterio AA equivalente que sustituya esa exigencia;
237. cumplimiento de `2.5.4 Actuación mediante movimiento`, nivel A, mediante ausencia de funciones activadas por movimientos físicos del dispositivo o del usuario;
238. conservación formal del nivel A de `2.5.4` al no existir un criterio AA equivalente que sustituya esa exigencia;
239. cumplimiento de `2.5.7 Movimientos de arrastre`, nivel AA, mediante ausencia de funciones que requieran arrastre como único mecanismo;
240. obligación de proporcionar una operación equivalente sin arrastre si una interacción de arrastre se incorpora posteriormente;
241. cumplimiento de `2.5.8 Tamaño del objetivo (mínimo)`, nivel AA;
242. adopción de `48px x 48px CSS` como mínimo general para los objetivos interactivos independientes propios de `sitio`;
243. superación del mínimo normativo de `24px x 24px CSS` establecido por `2.5.8`;
244. cambio de los subelementos de navegación desde `36px` hasta `48px` de altura mínima;
245. utilización del control completo como superficie interactiva en lugar de limitar el objetivo al texto, icono o elemento SVG interior;
246. aplicación del mínimo de `48px x 48px CSS` a navegación, grupos expandibles, controles globales, botones, campos, acciones de tarjetas, accesos de listado, acciones de regreso y enlaces independientes de Contactos;
247. conservación de los enlaces integrados dentro de texto como objetivos textuales mediante la excepción normativa correspondiente;
248. cumplimiento adicional de `2.5.5 Tamaño del objetivo (mejorado)`, nivel AAA, mediante objetivos independientes de `48px x 48px CSS`, respetando las excepciones normativas;
249. utilización del estado `hover` exclusivamente como retroalimentación visual adicional;
250. ausencia de funciones, contenido necesario o cambios de estado disponibles exclusivamente mediante `hover`;
251. apertura y cierre de grupos expandibles solamente mediante activación explícita;
252. utilización de una activación sencilla equivalente mediante ratón, tacto y lápiz;
253. ausencia de funciones propias que requieran gestos multipunto, recorridos específicos, formas dibujadas o pulsaciones prolongadas;
254. conservación de los gestos normales del navegador para desplazamiento, ampliación y demás funciones propias del agente de usuario;
255. ausencia de acciones definitivas ejecutadas mediante `pointerdown`, `mousedown` o `touchstart` como mecanismo general;
256. posibilidad de cancelar una interacción de puntero antes de completar la activación normal del control;
257. ausencia de arrastre obligatorio para reordenar, navegar, cambiar estados, seleccionar opciones o completar operaciones;
258. cumplimiento adicional de `2.5.6 Mecanismos de entrada concurrentes`, nivel AAA;
259. conservación simultánea de ratón, tacto, lápiz y teclado cuando los mecanismos se encuentran disponibles;
260. ausencia de desactivación de un mecanismo de entrada debido a la detección o utilización de otro;
261. ausencia de funciones activadas mediante sacudidas, inclinación u otros movimientos físicos;
262. tratamiento del cambio de orientación exclusivamente como cambio del espacio disponible y no como orden funcional;
263. conservación de las mismas reglas de interacción por puntero y tacto en los temas claro y oscuro;
264. integración de `@axe-core/playwright` con las pruebas ejecutadas mediante Playwright;
265. utilización de `axe-core` como motor de auditoría automática de accesibilidad;
266. configuración de la auditoría mediante las etiquetas `wcag2a`, `wcag2aa`, `wcag21a`, `wcag21aa` y `wcag22aa`;
267. exigencia de `0` violaciones en cada análisis automático de `axe-core`;
268. envío de los resultados no determinables automáticamente a comprobación manual;
269. conservación de la comprobación manual aunque la auditoría automática no informe violaciones;
270. exigencia de `100%` de aprobación de todas las pruebas automatizadas ejecutadas;
271. bloqueo de la promoción hacia `main` cuando una sola prueba automatizada falla;
272. utilización del porcentaje real de pruebas aprobadas en lugar de una puntuación estimativa de accesibilidad;
273. cobertura de accesibilidad para cada tipo conceptual de página;
274. cobertura independiente de los estados que cambian estructura, semántica o comportamiento;
275. comprobación de las representaciones visuales dependientes del tema en claro y oscuro;
276. cobertura de contenido en el idioma del sistema, contenido mediante respaldo, colecciones multilingües y cambios lingüísticos internos;
277. utilización de datos de prueba con cadenas extensas, contenido ancho y demás condiciones necesarias para ejercitar los límites de la interfaz;
278. comprobación automática y manual de la navegación mediante teclado;
279. comprobación automática de la gestión del foco mediante `document.activeElement`;
280. comprobación manual de la perceptibilidad, claridad y ausencia de ocultación del indicador de foco;
281. comprobación automática de la estructura semántica, relaciones y estados ARIA;
282. comprobación automática y manual de los nombres accesibles;
283. comprobación automática de `lang` y revisión manual de su correspondencia con el idioma real del contenido;
284. comprobación automática de la presencia y conservación de `alt` y revisión manual de la adecuación de las alternativas;
285. reproducción automática de la fórmula de contraste definida por la especificación;
286. fallo automático cuando una combinación cromática permitida queda por debajo del umbral correspondiente;
287. conservación de la comprobación manual para fondos variables y para la cobertura real de la capa de contraste de la cabecera;
288. comprobación automática del redimensionamiento del texto hasta `200%`;
289. comprobación automática del reflujo a `320px CSS`;
290. comprobación manual del caso equivalente de `1280px CSS` con ampliación del navegador al `400%`;
291. aplicación simultánea de los valores `1.5`, `2`, `0.12` y `0.16` durante las pruebas de espaciado textual;
292. comprobación de funcionamiento en orientación vertical y horizontal;
293. medición automática mediante `getBoundingClientRect()` de objetivos interactivos independientes de al menos `48px x 48px CSS`;
294. exclusión de los enlaces integrados dentro del texto de la exigencia general de `48px x 48px CSS`;
295. comprobación de los mismos flujos mediante ratón, tacto emulado y teclado cuando la automatización permite reproducirlos;
296. comprobación de la disponibilidad funcional en ausencia de `hover`;
297. comprobación de que las acciones definitivas no se ejecutan únicamente mediante `pointerdown`, `mousedown` o `touchstart`;
298. comprobación de la posibilidad de cancelar una interacción de puntero antes de completar la activación;
299. comprobación de ausencia de arrastre obligatorio;
300. comprobación automatizada de todos los estados semánticos del formulario;
301. comprobación automatizada de `aria-busy`, `aria-hidden` y exclusión del foco durante los estados de carga;
302. comprobación conjunta de `<title>`, `H1`, foco y cierre de navegación durante los cambios internos de página;
303. obligación de comprobar manualmente el comportamiento real mediante lector de pantalla;
304. exclusión de la comparación píxel a píxel como criterio suficiente de conformidad de accesibilidad;
305. integración de las pruebas automatizadas de accesibilidad dentro de la validación anterior a la promoción hacia `main`;
306. obligación de completar las comprobaciones manuales aplicables antes de promover cambios que afecten estructura, semántica, interacción, navegación, estados, presentación accesible o contenido editorial relacionado con accesibilidad.

Los modelos visuales deben utilizar los iconos concretos establecidos en el mapeo de esta especificación.

Las representaciones visuales finales de escritorio siguen constituyendo la referencia de identidad y composición para las páginas definidas, complementadas por las reglas responsive establecidas para escritorio intermedio y pantallas estrechas.

Los estados comunes definidos forman parte de la referencia de comportamiento visual para todas las páginas y regiones correspondientes.

La adaptación responsive definida en esta especificación forma parte de la referencia cerrada de diseño.

Las decisiones de accesibilidad incluidas en esta especificación forman parte de la referencia cerrada de la etapa de accesibilidad.

La auditoría de contraste queda cerrada para los temas claro y oscuro dentro de los usos permitidos definidos por esta especificación.

La gestión de contexto y foco durante los cambios de página queda cerrada para la navegación interna de la aplicación.

La semántica accesible del estado de envío en curso del formulario queda cerrada mediante el estado ocupado del formulario, los campos temporalmente de solo lectura, la indisponibilidad semántica y funcional del control de envío, la comunicación no interruptiva del progreso y la conservación del foco.

Las alternativas textuales de las imágenes de contenido quedan cerradas mediante la clasificación funcional correspondiente a cada representación, la responsabilidad de `sitio-api` sobre el valor final de `alt`, la representación directa de ese valor por `sitio`, las reglas concretas para `Sobre mí`, proyectos, artículos, certificados y certificaciones, y la utilización exclusiva de iconos en las tarjetas de Contactos.

El idioma semántico queda cerrado mediante la declaración del idioma activo del sistema en el documento, la declaración del idioma real de las partes que difieren de él, la conservación del idioma de las variantes presentadas mediante respaldo, la separación entre contenido e interfaz dentro de unidades multilingües y la conservación de los cambios lingüísticos definidos editorialmente dentro del contenido.

El redimensionamiento, el reflujo, el espaciado del texto y la orientación quedan cerrados mediante la escala tipográfica relativa, el soporte del aumento del texto hasta `200%`, la conservación del zoom del navegador, el reflujo hasta `320px CSS`, el crecimiento obligatorio de los contenedores textuales, la limitación del desplazamiento horizontal a contenido bidimensional necesario, el soporte de los valores de espaciado definidos por WCAG y el funcionamiento completo en ambas orientaciones.

La interacción por puntero y tacto queda cerrada mediante objetivos interactivos independientes de al menos `48px x 48px CSS`, la ampliación de los subelementos de navegación a `48px` de altura mínima, la independencia funcional respecto de `hover`, la activación sencilla mediante ratón, tacto y lápiz, la cancelación antes de completar una activación, la ausencia de arrastre y gestos complejos obligatorios, la conservación de los mecanismos de entrada concurrentes, la correspondencia entre etiqueta visible y nombre accesible y la ausencia de actuación funcional mediante movimiento físico.

Las pruebas de accesibilidad quedan cerradas mediante la integración de `@axe-core/playwright`, la exigencia de `0` violaciones automatizadas dentro del alcance configurado, la aprobación obligatoria del `100%` de la suite automatizada, la cobertura por páginas, estados, temas, contextos lingüísticos y mecanismos de interacción, y la conservación de comprobaciones manuales para los aspectos que requieren evaluación humana o tecnologías de asistencia reales.

Ninguna prueba manual impide el flujo automatizado de la promoción. Las pruebas manuales sinven de comprobación humana, por lo que no es posible formar parte del flujo automatizado de la promoción.

La etapa de responsive y accesibilidad queda cerrada mediante las reglas de adaptación estructural, contraste, foco, semántica, idioma, alternativas textuales, redimensionamiento, reflujo, orientación, interacción por puntero y tacto y la estrategia de pruebas definida en esta especificación.

La base tecnológica de Angular queda definida mediante la configuración de componentes independientes, enrutamiento, detección de cambios sin Zone.js, renderización del lado del cliente y construcción estática destinada a GitHub Pages.

El proyecto utiliza Angular `22.2`, TypeScript `6.0`, Node.js `24`, npm `12.2.0`, Tailwind CSS `4`, ESLint `10`, angular-eslint `22`, Prettier `3`, Vitest `5` y Playwright, con las configuraciones y responsabilidades establecidas en esta especificación.

La configuración del proyecto conserva la instalación reproducible de dependencias y las autorizaciones específicas para los scripts de instalación necesarios.

El análisis estático comprende el código TypeScript y las plantillas Angular. Las convenciones de formato se mantienen mediante Prettier y la configuración compatible del editor.

Las pruebas unitarias utilizan Vitest y V8, con umbrales de cobertura del `100%` para instrucciones, ramas, funciones y líneas. Las pruebas de navegador utilizan Chromium, Firefox y WebKit.

La versión del proyecto se administra mediante `package.json` y la versión de la aplicación mediante `public/version.json`. Ambas permanecen independientes y utilizan inicialmente `0.0.0`.

La rama `main` permanece protegida y la promoción utiliza una GitHub App exclusiva del repositorio `sitio`, con credenciales administradas mediante variables y secretos de GitHub Actions.

La integración continua queda distribuida entre cuatro workflows: validación de `dev`, promoción automática mediante `workflow_run`, promoción alternativa mediante pull request y construcción y publicación de GitHub Pages.

La promoción automática debe utilizar exclusivamente el commit validado. La promoción mediante pull request dispone de validaciones propias y conserva la comprobación del commit antes de su integración.

La publicación de GitHub Pages depende de una modificación de `public/version.json` en `main`, utiliza la ruta base `/sitio/` y publica el artefacto ubicado en `dist/sitio/browser/`.

La base tecnológica de la etapa 7 queda cerrada. La aplicación inicial dispone de construcción y pruebas satisfactorias, y la integración, la promoción mediante pull request y la publicación cuentan con ejecuciones comprobadas. La activación del workflow independiente de promoción mediante `workflow_run` permanece pendiente de verificación funcional.

Esta especificación constituye la referencia base de identidad visual, responsive, accesibilidad definida y comportamiento visual para las siguientes etapas de diseño e implementación de `sitio`.

Volver al índice [aquí](../README.md#índice-1).
