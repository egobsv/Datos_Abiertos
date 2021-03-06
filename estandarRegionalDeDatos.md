# Perfil Regional de Metadatos

![N|Solid](https://github.com/raulvelas/datosabiertos/blob/master/esquema%20regional%20datos%20abiertos.png)

## Campos del perfil
## Catalogo (catalog)
<table class="docutils">

<tr><th>Nombre                                     </th><th>Requerido  </th><th>Descripción                                                                                                                                                                                                                                                </th><th>Ejemplo                                                        </th><th>Variable             </th><th>Tipo           </th></tr>
</thead>
<tbody>
<tr><td>Identificador                              </td><td>R          </td><td>Es el identificador único del catálogo dentro de la red de catálogos de datos abiertos a la que pertenece. Este identificador puede ser otorgado por el área a cargo de la política de apertura de un país a sus organismos, o establecido por alguna convención internacional para el caso de catálogos de jerarquía jurisdiccional nacional.

El identificador debe ser una o más palabras en minúsculas, separadas con guiones medios, sin usar caracteres especiales. Identifica en forma breve, sucinta y declarativa al catálogo.                                                                                                                                                                                                                                                            </td><td>"energia"

"desarrollo-social"

"justicia"

"El Salvador"

"mexico"                                                                </td><td>identifier           </td><td>String         </td></tr>
<tr><td>Título                                     </td><td>Si         </td><td>Nombre dado al catálogo. Debe ser claro, breve y lo suficientemente abstracto como para abarcar la multiplicidad de datasets que contiene.                                                                                                                 </td><td>Datos El Salvador                                                </td><td>title                </td><td>String         </td></tr>
<tr><td>Descripción                                </td><td>Si         </td><td>Descripción del contenido del catálogo.                                                                                                                                                                                                                    </td><td>Portal de Datos Abiertos del Gobierno de El Salvador</td><td>description          </td><td>String         </td></tr>
<tr><td>Autor                                      </td><td>Si         </td><td>Autoridad responsable de la publicación del catálogo.                                                                                                                                                                                                      </td><td>Ministerio de Modernización                                    </td><td>publisher -&gt; name    </td><td>String         </td></tr>
<tr><td>Correo electrónico del autor               </td><td>Si         </td><td>Correo electrónico de contacto de la autoridad responsable de la publicación del catálogo.                                                                                                                                                                 </td><td>lcruz@presidencia.gob.sv                                     </td><td>publisher -&gt; mbox    </td><td>String         </td></tr>
<tr><td>Datasets                                   </td><td>Si         </td><td>Contiene una lista de los datasets que forman parte del catálogo.                                                                                                                                                                                          </td><td>[{...}, {...}]                                                 </td><td>dataset              </td><td>Array          </td></tr>
<tr><td>Fecha de creación o publicación            </td><td>R          </td><td>Fecha de creación o publicación del catálogo. Se escribe según el formato ISO-8601, tipeado como fecha simple o fecha con hora, con el mayor detalle posible que sea relevante para el dataset.                                                            </td><td>"2016-04-14T19:48:05.433640" para especificar fecha y hora

"2016-04-14" para especificar fecha únicamente                                                                </td><td>issued               </td><td>String         </td></tr>
<tr><td>Fecha de última actualización/ modificación</td><td>R          </td><td>Fecha de última actualización/modificación del catálogo (ya sea de sus datos o de sus metadatos). Se escribe según el formato ISO-8601, tipeado como fecha simple o fecha con hora, con el mayor detalle posible que sea relevante para el dataset.        </td><td>"2016-04-19T19:48:05.433640" para especificar fecha y hora

"2016-04-19" para especificar fecha únicamente                                                                </td><td>modified             </td><td>String         </td></tr>
<tr><td>Fecha de última actualización/ modificación</td><td>No         </td><td>Fecha de última actualización/modificación de los datos del catálogo. Según el formato ISO-8601, tipeado como fecha simple o fecha con hora, con el mayor detalle posible que sea relevante para el catálogo.                                              </td><td>"2016-04-19T19:48:05.433640" para especificar fecha y hora

"2016-04-19" para especificar fecha únicamente                                                                </td><td>dataModified         </td><td>String         </td></tr>
<tr><td>Fecha de última actualización/ modificación</td><td>No         </td><td>Fecha de última actualización/modificación de los metadatos del catálogo. Según el formato ISO-8601, tipeado como fecha simple o fecha con hora, con el mayor detalle posible que sea relevante para el catálogo.                                          </td><td>"2016-04-19T19:48:05.433640" para especificar fecha y hora

"2016-04-19" para especificar fecha únicamente                                                                </td><td>metadataModified     </td><td>String         </td></tr>
<tr><td>Idioma(s)                                  </td><td>R          </td><td>Lenguaje para la descripción de los metadatos de los datasets contenidos en el catálogo. Hay 2 estándares ISO que pueden ser utilizados para este campo:

(a) ISO 639-1 (2 letras)
(b) ISO 639-2/T (3 letras) es el más recomendado.

Puede definirse 1 o más lenguajes en una lista. (Link a los estándares ISO: https://www.loc.gov/standards/iso639-2/php/code_list.php)                                                                                                                                                                                                                                                            </td><td>["es"] para un lenguaje ISO 639-1

["spa", ”eng"] para dos lenguajes ISO 639-2                                                                </td><td>language             </td><td>Array          </td></tr>
<tr><td>Taxonomía temática                         </td><td>R          </td><td>Es el sistema de clasificación temática, creado por la organización responsable del catálogo.

Compone una lista de temas que se pueden usar para clasificar los datasets del catálogo. Si se clasifica a algún dataset del catálogo como perteneciente a uno o más temas, este campo es obligatorio ya que se debe explicitar una taxonomía temática para poder usar sus temas.

Para catálogos nacionales o que reúnen datasets de temáticas variadas, se recomienda utilizar la taxonomía temática de la Unión Europea (Ver standards/themeTaxonomy).                                                                                                                                                                                                                                                            </td><td>[{...}, {...}]                                                 </td><td>themeTaxonomy        </td><td>Array          </td></tr>
<tr><td>Licencia                                   </td><td>R          </td><td>Indica la licencia bajo la cual todos los datasets y distribuciones del catálogo están disponibles mediante un enlace a la licencia o documento de la licencia seleccionada, o mediante el título textual de la licencia tal como aparece en la lista de http://opendefinition.org/licenses/.

Se recomienda utilizar la licencia "Open Database License (ODbL) v1.0". Un dataset o distribución que especifique una licencia diferente, sobreescribe a la licencia general del catálogo.                                                                                                                                                                                                                                                            </td><td>"http://opendatacommons.org/licenses/dbcl/1-0/" si se utiliza un enlace

"Open Database License (ODbL) v1.0" si se consigna el nombre de la licencia a utilizar                                                                </td><td>license              </td><td>String         </td></tr>
<tr><td>Página web del catálogo                    </td><td>R          </td><td>Dirección web o enlace de acceso a la página principal del catálogo                                                                                                                                                                                        </td><td>http://datos.gob.sv                                            </td><td>homepage             </td><td>String         </td></tr>
<tr><td>Derechos sobre el catálogo                 </td><td>No         </td><td>Información sobre derechos aplicables al catálogo en el caso que no se hayan especificado en la licencia. Los datasets y sus distribuciones heredan la información sobre derechos aplicables al catálogo, a menos que especifiquen unos derechos distintos.</td><td>nan                                                            </td><td>rights               </td><td>String         </td></tr>
<tr><td>Cobertura geográfica                       </td><td>No         </td><td>El área geográfica cubierta por el catálogo.

Una región o un lugar determinado. Puede tomar valores:

a) de países y, provincias y municipios argentinos, según las recomendaciones de la “Guía para la identificación y uso de entidades interoperables”.
b) un área de coordenadas representada por latitud/ longitud en el orden: minima longitud, minima latitud, maxima longitud, maxima latitud.
c) un punto geográfico representado por latitud/longitud.
d) Si la referencia geográfico no está identificada en la “Guía para la identificación y uso de entidades interoperables” indicar la URIs según geonames.org; ej :
http://sws.geonames.org/6255146                                                                                                                                                                                                                                                            </td><td>"ARG" es el código para la República Argentina.

"06007" es el código de un departamento

[-58.111111, -35.111111, -57.111111, -33.111111] es un bounding box

[-58.111111, -35.111111] es un punto geográfico

"http://sws.geonames.org/6255146"                                                                </td><td>spatial              </td><td>String or Array</td></tr>
<tr><td>Version del perfil de metadatos            </td><td>R          </td><td>Es la versión del perfil de metadatos utilizada en el catálogo.

Se utiliza para que distintas aplicaciones reconozcan y validen los metadatos del catálogo, y las funcionalidades disponibles para distintos fines.                                                                                                                                                                                                                                                            </td><td>1.0                                                            </td><td>metadataSchemeVersion</td><td>String         </td></tr>
</tbody>
</table>

## Dataset (dataset)

<table class="docutils">
<thead>
<tr><th>Nombre                                         </th><th>Requerido  </th><th>Descripción                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         </th><th>Ejemplo                                                                                                                                        </th><th>Variable                </th><th>Tipo           </th></tr>
</thead>
<tbody>
<tr><td>Identificador                                  </td><td>Si         </td><td>Identificador único del dataset, este identificador debe ser único para todo el catálogo.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           </td><td>"dataset-ejemplo-35782”                                                                                                                        </td><td>identifier              </td><td>String         </td></tr>
<tr><td>Título                                         </td><td>Si         </td><td>Nombre asignado al dataset tal como será publicado.

Debe ser claro y lo suficientemente abstracto como para abarcar la multiplicidad de distribuciones que contiene. Se recomienda no exceder los 100 caracteres en la mayoría de los casos.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     </td><td>Sistema de contrataciones electrónicas                                                                                                         </td><td>title                   </td><td>String         </td></tr>
<tr><td>Descripción                                    </td><td>Si         </td><td>Descripción del contenido del dataset de un modo claro y conciso.

Se recomienda no exceder los 500 caracteres en la mayoría de los casos.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     </td><td>Datos correspondiente al Sistema de Contrataciones Electrónicas (Argentina Compra)                                                             </td><td>description             </td><td>String         </td></tr>
<tr><td>Autor                                          </td><td>Si         </td><td>Autoridad responsable de la publicación del dataset. 

Se recomienda adoptar un vocabulario controlado con las dependencias del país de que se trate y definir una forma de expresar la pertenencia jerárquica de la organización (Ej.: utilizar puntos o guiones medios para separar niveles jerárquicos, expresarlos en forma descendente o ascendente, etc.)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     </td><td>Ministerio de Modernización. Secretaría de Modernización Administrativa. Oficina Nacional de Contrataciones.                                   </td><td>publisher -&gt; name       </td><td>String         </td></tr>
<tr><td>Correo electrónico del autor                   </td><td>R          </td><td>Correo electrónico de contacto de la autoridad responsable de la publicación del dataset.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           </td><td>onc@modernizacion.gob.ar                                                                                                                       </td><td>publisher -&gt; mbox       </td><td>String         </td></tr>
<tr><td>Área/Persona de contacto                       </td><td>R          </td><td>Área/persona de contacto que puede brindar información relevante sobre el dataset. Este es un punto de contacto más próximo al mantenimiento u operación de este dataset.                                                                                                                                                                                                                                                                                                                                                                                                           </td><td>Ministerio de Modernización. Secretaría de Modernización Administrativa. Oficina Nacional de Contrataciones. Dirección de Compras Electrónicas.</td><td>contactPoint -&gt; fn      </td><td>String         </td></tr>
<tr><td>Correo electrónico del área/persona de contacto</td><td>R          </td><td>Correo electrónico del área/persona de contacto que puede brindar información relevante sobre el dataset.                                                                                                                                                                                                                                                                                                                                                                                                                                                                           </td><td>onc-compraselectronicas@modernizacion.gob.ar                                                                                                   </td><td>contactPoint -&gt; hasEmail</td><td>String         </td></tr>
<tr><td>Fuente primaria                                </td><td>No         </td><td>Fuente original o primaria de los datos publicados en el dataset. Se utiliza cuando la entidad responsable de la publicación del dataset, no es la entidad que produce los datos.                                                                                                                                                                                                                                                                                                                                                                                                   </td><td>Ministerio de Hacienda. Instituto Nacional de Estadísticas y Censos. Dirección Nacional de Cuentas Nacionales.                                 </td><td>attribution             </td><td>String         </td></tr>
<tr><td>Colaboradores                                  </td><td>No         </td><td>Entidades, organizaciones o personas adicionales que son o fueron responsables de recolectar, crear o contribuir en forma alguna al desarrollo del activo de datos. Los valores deben separarse por comas.                                                                                                                                                                                                                                                                                                                                                                          </td><td>Instituto Argentino de Análisis Fiscal                                                                                                         </td><td>contributor             </td><td>String         </td></tr>
<tr><td>Distribuciones                                 </td><td>Si         </td><td>Lista de distribuciones que pertenecen al dataset y sus metadatos. Cada distribución se representa con un objeto ("{}") donde se describen los metadatos especificados para la clase "distribution" de este perfil de metadatos.                                                                                                                                                                                                                                                                                                                                                    </td><td>[{...}, {...}]                                                                                                                                 </td><td>distribution            </td><td>Array          </td></tr>
<tr><td>Temática(s)                                    </td><td>R          </td><td>Temática/s o categoría/s a la/s que se refiere el dataset al ser publicado.

Un dataset puede pertenecer a más de una categoría temática, de manera que el tipo de valor de este campo es una lista de categorías. La taxonomía a utilizar debe ser creada por la autoridad responsable del catálogo. Se deben usar los ids (ver campo "id" de la clase Theme) de los temas definidos en la taxonomía para componer la lista (no se deben usar las etiquetas ni las descripciones).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     </td><td>["gove", "econ"]                                                                                                                               </td><td>theme                   </td><td>Array          </td></tr>
<tr><td>Fecha de publicación                           </td><td>Si         </td><td>Fecha de publicación del dataset. Según el formato ISO-8601, tipeado como fecha simple o fecha con hora, con el mayor detalle posible que sea relevante para el dataset.                                                                                                                                                                                                                                                                                                                                                                                                            </td><td>"2016-04-14T19:48:05.433640" para especificar fecha y hora

"2016-04-14" para especificar fecha únicamente                                                                                                                                                </td><td>issued                  </td><td>String         </td></tr>
<tr><td>Fecha de última actualización/ modificación    </td><td>R          </td><td>Fecha de última actualización/modificación de dataset (ya sea de sus datos o de sus metadatos). Según el formato ISO-8601, tipeado como fecha simple o fecha con hora, con el mayor detalle posible que sea relevante para el dataset.                                                                                                                                                                                                                                                                                                                                              </td><td>"2016-04-19T19:48:05.433640" para especificar fecha y hora

"2016-04-19" para especificar fecha únicamente                                                                                                                                                </td><td>modified                </td><td>String         </td></tr>
<tr><td>Fecha de última actualización/ modificación    </td><td>R          </td><td>Fecha de última actualización/modificación de los datos del dataset. Según el formato ISO-8601, tipeado como fecha simple o fecha con hora, con el mayor detalle posible que sea relevante para el dataset.                                                                                                                                                                                                                                                                                                                                                                         </td><td>"2016-04-19T19:48:05.433640" para especificar fecha y hora

"2016-04-19" para especificar fecha únicamente                                                                                                                                                </td><td>dataModified            </td><td>String         </td></tr>
<tr><td>Fecha de última actualización/ modificación    </td><td>R          </td><td>Fecha de última actualización/modificación de los metadatos del dataset. Según el formato ISO-8601, tipeado como fecha simple o fecha con hora, con el mayor detalle posible que sea relevante para el dataset.                                                                                                                                                                                                                                                                                                                                                                     </td><td>"2016-04-19T19:48:05.433640" para especificar fecha y hora

"2016-04-19" para especificar fecha únicamente                                                                                                                                                </td><td>metadataModified        </td><td>String         </td></tr>
<tr><td>Frecuencia de actualización                    </td><td>Si         </td><td>Frecuencia con la que se actualiza el dataset.

Se recomienda especificar períodos normalizados con formato ISO-8601, agregando el campo “eventual” para datasets que se publican con una frecuencia eventual o no especificada. Anexo "Especificación de frecuencias según ISO-8601".                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     </td><td>“R/P1Y” para datasets que se actualizan anualmente                                                                                             </td><td>accrualPeriodicity      </td><td>String         </td></tr>
<tr><td>Página de referencia                           </td><td>R          </td><td>URL de la página web a través de la cual se puede acceder al dataset, sus recursos o información adicional sobre el mismo.                                                                                                                                                                                                                                                                                                                                                                                                                                                          </td><td>http://datos.gob.ar/dataset/sistema-de-contrataciones-electronicas-argentina-compra                                                            </td><td>landingPage             </td><td>String         </td></tr>
<tr><td>Etiqueta(s)                                    </td><td>R          </td><td>Palabras que describen el título o el contenido del recurso.

Es necesario que las etiquetas se encuentren correctamente escritas, en plural y respetando la existencia de tags anteriores. Etiquetas que colaboran en la búsqueda de los usuarios. Cuanto más amplia y uniforme sea la lista de tags mayor será su eficiencia. A tales fines se recomienda ver el Anexo “Pautas para la selección de etiquetas”.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     </td><td>["bienes", "compras","contrataciones"]                                                                                                         </td><td>keyword                 </td><td>Array          </td></tr>
<tr><td>Cobertura temporal                             </td><td>R          </td><td>Período de tiempo cubierto por el dataset.

El intervalo de tiempo está formado por una fecha de inicio y una de fin separadas por “/”, en formato ISO 8601, con el nivel de especificidad requerido por el dataset. Opcionalmente, se puede especificar una sola fecha (en lugar de dos) y esta se interpretará como la fecha de inicio, mientras que el final permanece no especificado.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     </td><td>2015-01-01/2015-12-31

2015-01-01T00:45:00Z/2016-01-15T00:06:00Z

2015-01-01

2015-01-01T00:45:00Z                                                                                                                                                </td><td>temporal                </td><td>String         </td></tr>
<tr><td>Licencia                                       </td><td>R          </td><td>Indica la licencia bajo la cual el dataset y todas sus distribuciones están disponibles mediante un enlace a la licencia o documento de la licencia seleccionada, o mediante el título textual de la licencia tal como aparece en la lista de http://opendefinition.org/licenses/ . Se recomienda utilizar la licencia "Open Database License (ODbL) v1.0". Un dataset hereda por default la licencia general del catálogo salvo que se especifique una licencia diferente en este campo. Las distribuciones del dataset heredan esta licencia salvo que especifiquen una diferente.</td><td>"http://opendatacommons.org/licenses/dbcl/1-0/" si se utiliza un enlace

"Open Database License (ODbL) v1.0" si se consigna el nombre de la licencia a utilizar                                                                                                                                                </td><td>license                 </td><td>String         </td></tr>
<tr><td>Idioma(s)                                      </td><td>No         </td><td>Lenguaje para la descripción de los metadatos del dataset. Hay 2 estándares ISO que pueden ser utilizados para este campo:

(a) ISO 639-1 (2 letras)
(b) ISO 639-2/T (3 letras) es el más recomendado.

Puede definirse 1 o más lenguajes en una lista. Los lenguajes especificados para un dataset, sobreesriben a los del catálogo. Si este campo está vacío el dataset hereda los lenguajes del catálogo. (Link a los estándares ISO: https://www.loc.gov/standards/iso639-2/php/code_list.php)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     </td><td>["es"] para un lenguaje ISO 639-1

["spa", ”eng"] para dos lenguajes ISO 639-2                                                                                                                                                </td><td>language                </td><td>Array          </td></tr>
<tr><td>Cobertura geográfica                           </td><td>No         </td><td>Una región o lugar determinado al que el dataset haga referencia.

Una región o un lugar determinado. Puede tomar valores:

a) de países y, provincias y municipios argentinos, según las recomendaciones de la “Guía para la identificación y uso de entidades interoperables”.
b) un área de coordenadas representada por latitud/ longitud en el orden: minima longitud, minima latitud, maxima longitud, maxima latitud.
c) un punto geográfico representado por latitud/longitud.
d) Si la referencia geográfico no está identificada en la “Guía para la identificación y uso de entidades interoperables” indicar la URIs según geonames.org; ej :
http://sws.geonames.org/6255146"                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     </td><td>"ARG" es el código para la República Argentina.

"06007" es el código de un departamento

[-58.111111, -35.111111, -57.111111, -33.111111] es un bounding box

[-58.111111, -35.111111] es un punto geográfico

"http://sws.geonames.org/6255146"                                                                                                                                                </td><td>spatial                 </td><td>Array or String</td></tr>
<tr><td>Jerarquía, orden o nivel jurisdiccional        </td><td>No         </td><td>Clasificación del dataset por su jerarquía, orden o nivel jurisdiccional. Indica el tipo y alcance de la jurisdicción legal que está detrás de la publicación del dataset. 

El valor puede ser "national" o "territorial" (cubriendo el caso nacional por un lado y todas las jurisdicciones sub-nacionales por otro), o pertenecer a un vocabulario controlado alternativo definido por el país o la organización responsable de la política de apertura (Ej.: "federal", "provincial" o "municipal").                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     </td><td>"national"

"territorial"                                                                                                                                                </td><td>jurisdiction            </td><td>String         </td></tr>
</tbody>
</table>

## Distribución (distribution)

<table class="docutils">
<thead>
<tr><th>Nombre                                     </th><th>Requerido  </th><th>Descripción                                                                                                                                                                                                                                                                                                                                                                                                                                                                     </th><th>Ejemplo                                                                                                                                   </th><th>Variable         </th><th>Tipo   </th></tr>
</thead>
<tbody>
<tr><td>Identificador                              </td><td>Si         </td><td>Identificador único de la distribución, este identificador debe ser único para la distribución dentro del catálogo completo.

Debe estar compuesto por letras mayúsculas o minúsculas de la "a" a la "z" sin caracteres especiales (sin tildes y sin la "ñ"), números, guiones bajos "_", guiones medios "-" y puntos ".".                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 </td><td>1.2                                                                                                                                       </td><td>identifier       </td><td>String </td></tr>
<tr><td>Título                                     </td><td>Si         </td><td>Nombre asignado a la distribución.                                                                                                                                                                                                                                                                                                                                                                                                                                              </td><td>Convocatorias abiertas durante el año 2015                                                                                                </td><td>title            </td><td>String </td></tr>
<tr><td>Descripción                                </td><td>R          </td><td>Breve descripción de la distribución. Se recomienda no escribir más de una línea. Toda información adicional puede ser incluida en la descripción del dataset.                                                                                                                                                                                                                                                                                                                  </td><td>Listado de las convocatorias abiertas durante el año 2015 en el sistema de contrataciones electrónicas                                    </td><td>description      </td><td>String </td></tr>
<tr><td>URL de descarga                            </td><td>Si         </td><td>URL que permite la descarga directa de la distribución del dataset, vincula directamente a un archivo descargable en un formato dado.                                                                                                                                                                                                                                                                                                                                           </td><td>http://datos.gob.ar/dataset/becaceb2-dbd0-4879-93bd-5f02bd3b8ca2/resource/bf2f67f4-9ab3-479b-a881-56b43565125e/download/contratos-2015.csv</td><td>downloadURL      </td><td>String </td></tr>
<tr><td>URL de acceso                              </td><td>Si         </td><td>URL que permite el acceso a la distribución del dataset. Puede ser una página, feed u otro tipo de recurso que dé acceso indirecto a las distribuciones. Si las distribuciones son solo accesibles a través de la página de referencia del dataset, debe completarse el valor de la URL de acceso a la distribución con el mismo valor de la página de referencia del dataset.                                                                                                  </td><td>http://datos.gob.ar/dataset/sistema-de-contrataciones-electronicas-argentina-compra/archivo/fa3603b3-0af7-43cc-9da9-90a512217d8a          </td><td>accessURL        </td><td>String </td></tr>
<tr><td>Campos de la distribución                  </td><td>R          </td><td>Lista de campos que contiene una distribución tabular (no aplica para aquellas distribuciones que no sean tablas) y sus metadatos. Cada campo se representa con un objeto ("{}") donde se describen los metadatos especificados para la clase "field" de este perfil de metadatos (como "nombre", "tipo" y "descripción").                                                                                                                                                      </td><td>[{...}, {...}]                                                                                                                            </td><td>field            </td><td>Array  </td></tr>
<tr><td>Fecha de publicación                       </td><td>Si         </td><td>Fecha de publicación de la distribución. Según el formato ISO-8601, tipeado como fecha simple o fecha con hora, con el mayor detalle posible que sea relevante para el dataset.                                                                                                                                                                                                                                                                                                 </td><td>"2016-04-14T19:48:05.433640" para especificar fecha y hora

"2016-04-14" para especificar fecha únicamente                                                                                                                                           </td><td>issued           </td><td>String </td></tr>
<tr><td>Fecha de última actualización/ modificación</td><td>R          </td><td>Fecha de última actualización/modificación de la distribución. Según el formato ISO-8601, tipeado como fecha simple o fecha con hora, con el mayor detalle posible que sea relevante para el dataset.                                                                                                                                                                                                                                                                           </td><td>"2016-04-19T19:48:05.433640" para especificar fecha y hora

"2016-04-19" para especificar fecha únicamente                                                                                                                                           </td><td>modified         </td><td>String </td></tr>
<tr><td>Fecha de última actualización/ modificación</td><td>R          </td><td>Fecha de última actualización/modificación de los datos del distribución. Según el formato ISO-8601, tipeado como fecha simple o fecha con hora, con el mayor detalle posible que sea relevante para el distribución.                                                                                                                                                                                                                                                           </td><td>"2016-04-19T19:48:05.433640" para especificar fecha y hora

"2016-04-19" para especificar fecha únicamente                                                                                                                                           </td><td>dataModified     </td><td>String </td></tr>
<tr><td>Fecha de última actualización/ modificación</td><td>R          </td><td>Fecha de última actualización/modificación de los metadatos del distribución. Según el formato ISO-8601, tipeado como fecha simple o fecha con hora, con el mayor detalle posible que sea relevante para el distribución.                                                                                                                                                                                                                                                       </td><td>"2016-04-19T19:48:05.433640" para especificar fecha y hora

"2016-04-19" para especificar fecha únicamente                                                                                                                                           </td><td>metadataModified </td><td>String </td></tr>
<tr><td>Formato del archivo                        </td><td>R          </td><td>Indica el formato del archivo de la distribución. Si el tipo de la distribución está definido por IANA (http://www.iana.org/assignments/media-types/media-types.xml), debe usarse esa definición. En caso contrario deberán ponerse los caracteres después del punto final del archivo, que determinan el formato (cuando no está definido por IANA).                                                                                                                           </td><td>"text/csv" definición de IANA

"csv" caracteres finales después del punto                                                                                                                                           </td><td>format           </td><td>String </td></tr>
<tr><td>Licencia                                   </td><td>R          </td><td>Indica la licencia bajo la cual la distribución está disponible mediante un enlace a la licencia o documento de la licencia seleccionada, o mediante el título textual de la licencia tal como aparece en la lista de http://opendefinition.org/licenses/ . Se recomienda utilizar la licencia "Open Database License (ODbL) v1.0". Una distribución hereda por default la licencia del dataset al que pertenece, salvo que se especifique una licencia diferente en este campo.</td><td>"http://opendatacommons.org/licenses/dbcl/1-0/" si se utiliza un enlace

"Open Database License (ODbL) v1.0" si se consigna el nombre de la licencia a utilizar                                                                                                                                           </td><td>license          </td><td>String </td></tr>
<tr><td>Tipo de archivo                            </td><td>No         </td><td>Indica el tipo de archivo de la distribución, sólo si este está definido por IANA (http://www.iana.org/assignments/media-types/media-types.xml). En caso contrario este campo permanece vacío.                                                                                                                                                                                                                                                                                  </td><td>"text/csv" definición de IANA

"" cuando el formato no tiene definición en IANA                                                                                                                                           </td><td>mediaType        </td><td>String </td></tr>
<tr><td>Tamaño                                     </td><td>No         </td><td>Tamaño de la distribución en bytes. El tamaño puede ser aproximado cuando no se conozca el tamaño exacto.                                                                                                                                                                                                                                                                                                                                                                       </td><td>Ejemplo para un archivo de 5Kb aproximadamente: ”5120”                                                                                    </td><td>byteSize         </td><td>Integer</td></tr>
<tr><td>Derechos sobre la distribución             </td><td>No         </td><td>Información sobre derechos aplicables a la distribución que no se hayan especificado en la licencia. Si se especifican, estos derechos sobreescriben a los del catálogo. En caso contrario, las distribuciones heredan los derechos especificados para el catálogo.                                                                                                                                                                                                             </td><td>nan                                                                                                                                       </td><td>rights           </td><td>String </td></tr>
<tr><td>Tipo de distribución                       </td><td>R          </td><td>Indica el tipo de recurso.

+ "Archivo de datos" (file): archivo físico de algún formato de datos que se puede descargar.
+ "API" (api): documentación en línea de un servicio web de datos.
+ "Código" (code): repositorio o archivo con scripts utilizados para la generación, transformación, limpieza o validación de los datos de todo o parte del dataset.
+ "Documentación" (documentation): documentación metodológica sobre los datos de todo o parte del dataset.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 </td><td>"file"                                                                                                                                    </td><td>type             </td><td>String </td></tr>
<tr><td>Identificador del dataset                  </td><td>Si         </td><td>La clave que identifica al conjunto de datos al que pertenece (y bajo el que se agrupa) este recurso.                                                                                                                                                                                                                                                                                                                                                                           </td><td>"dataset-ejemplo-35782”                                                                                                                   </td><td>datasetIdentifier</td><td>String </td></tr>
<tr><td>Cobertura temporal                         </td><td>No         </td><td>Período de tiempo cubierto por la distribución.

El intervalo de tiempo está formado por una fecha de inicio y una de fin separadas por “/”, en formato ISO 8601, con el nivel de especificidad requerido por el dataset. Opcionalmente, se puede especificar una sola fecha (en lugar de dos) y esta se interpretará como la fecha de inicio, mientras que el final permanece no especificado.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 </td><td>2015-01-01/2015-12-31

2015-01-01T00:45:00Z/2016-01-15T00:06:00Z

2015-01-01

2015-01-01T00:45:00Z                                                                                                                                           </td><td>temporal         </td><td>String </td></tr>
<tr><td>Cobertura geográfica                       </td><td>No         </td><td>Una región o lugar determinado al que el dataset haga referencia.

Una región o un lugar determinado. Puede tomar valores:

a) de países y, provincias y municipios argentinos, según las recomendaciones de la “Guía para la identificación y uso de entidades interoperables”.
b) un área de coordenadas representada por latitud/ longitud en el orden: minima longitud, minima latitud, maxima longitud, maxima latitud.
c) un punto geográfico representado por latitud/longitud.
d) Si la referencia geográfico no está identificada en la “Guía para la identificación y uso de entidades interoperables” indicar la URIs según geonames.org; ej :
http://sws.geonames.org/6255146"                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 </td><td>"ARG" es el código para la República Argentina.

"06007" es el código de un departamento

[-58.111111, -35.111111, -57.111111, -33.111111] es un bounding box

[-58.111111, -35.111111] es un punto geográfico

"http://sws.geonames.org/6255146"                                                                                                                                           </td><td>spatial          </td><td>String </td></tr>
<tr><td>Nomencladores utilizados                   </td><td>No         </td><td>Nombres de los estándares de los códigos, nomencladores o clasificadores utilizados en la distribución.                                                                                                                                                                                                                                                                                                                                                                         </td><td>ISO 8601                                                                                                                                  </td><td>codelists        </td><td>String </td></tr>
<tr><td>URLs documentación nomencladores           </td><td>No         </td><td>Hipervínculos a las fuentes oficiales de los códigos y estándares utilizados.                                                                                                                                                                                                                                                                                                                                                                                                   </td><td>https://www.w3.org/TR/NOTE-datetime                                                                                                       </td><td>codelistlink     </td><td>String </td></tr>
</tbody>
</table>

## Campo (field)

<table class="docutils">
<thead>
<tr><th>Nombre              </th><th>Requerido  </th><th>Descripción                                                                                                                                                                                                 </th><th>Ejemplo                                                                                                                                                                                                                                                                                    </th><th>Variable   </th><th>Tipo  </th></tr>
</thead>
<tbody>
<tr><td>Nombre              </td><td>R          </td><td>El nombre del campo tal como se denomina en el encabezado de la distribución. Véase la "Guía para la publicación de datos en formatos abiertos" para una adecuada elección del nombre de un campo.

Se recomienda no exceder los 40 caracteres en la mayoría de los casos. En caso de que un título más largo se juzgue necesario o significativamente más claro, este no deberá exceder los 60 caracteres en ningún caso.

Debe estar compuesto por letras minúsculas de la "a" a la "z" sin caracteres especiales (sin tildes y sin la "ñ"), números y guiones bajos "_".                                                                                                                                                                                                             </td><td>Ejemplo para el cuarto campo de la distribución "Convocatorias abiertas durante el año 2015", valor para el nombre: "unidad_operativa_contrataciones_desc"                                                                                                                                 </td><td>title      </td><td>String</td></tr>
<tr><td>Tipo                </td><td>R          </td><td>El tipo de dato contenido en el campo según la lista utilizada por la librería recline.js (http://okfnlabs.org/recline/docs/models.html#types). 

Los tipos incluidos en esta lista son:

string (text): Valores de texto.
number (double, float, numeric): Números que puedan no ser enteros (incluyen decimales).
integer (int): Números que siempre son enteros.
date: Fecha simple expresada según el estándar ISO 8601 incluyendo únicamente año, mes y día (YYYY-MM-DD) como en "2016-02-01".
time: Tiempo expresado según el estándar ISO 8601 incluyendo únicamente horas, minutos y segundos (hh:mm:ss) como en "10:05:00".
date-time (datetime, timestamp): Fecha completa expresada según el estándar ISO 8601 incluyendo año, mes, día, horas, minutos y segundos (YYYY-MM-DDThh:mm:ssZ) como en "2016-02-01T10:05:00+03:00"
boolean (bool): Valores verdadero/falso.
binary: Representación de datos binarios base64.
geo_point: Ver estructura en https://www.elastic.co/guide/en/elasticsearch/reference/current/geo-point.html.
geojson: Ver en http://geojson.org/
array: Lista de valores.
object (json): Objeto de JSON.
any: Campo que puede contener valores de cualquier tipo.                                                                                                                                                                                                             </td><td>Ejemplo para el campo "unidad_operativa_contrataciones_desc" de la distribución "Convocatorias abiertas durante el año 2015", valor para tipo: "string"                                                                                                                                    </td><td>type       </td><td>String</td></tr>
<tr><td>Descripción         </td><td>R          </td><td>La descripción completa de la información que contiene el campo. Debe ser suficientemente precisa y explicativa para que el usuario de los datos comprenda cabalmente cómo utilizar los datos de este campo.</td><td>Ejemplo para el campo "unidad_operativa_contrataciones_desc" de la distribución "Convocatorias abiertas durante el año 2015", valor para descripción: "Organismo que realiza la convocatoría. Organismo de máximo nivel jerárquico al que pertenece la unidad operativa de contrataciones."</td><td>description</td><td>String</td></tr>
<tr><td>Unidad de medida    </td><td>No         </td><td>La descripción de la unidad de medida en la que están expresados los valores del campo. Sólo se utiliza para campos de tipo numérico.                                                                       </td><td>Millones de pesos a precios de 1993                                                                                                                                                                                                                                                        </td><td>units      </td><td>String</td></tr>
<tr><td>Cobertura geográfica</td><td>No         </td><td>Una región o lugar determinado al que el dataset haga referencia.

Una región o un lugar determinado. Puede tomar valores:

a) de países y, provincias y municipios argentinos, según las recomendaciones de la “Guía para la identificación y uso de entidades interoperables”.
b) un área de coordenadas representada por latitud/ longitud en el orden: minima longitud, minima latitud, maxima longitud, maxima latitud.
c) un punto geográfico representado por latitud/longitud.
d) Si la referencia geográfico no está identificada en la “Guía para la identificación y uso de entidades interoperables” indicar la URIs según geonames.org; ej :
http://sws.geonames.org/6255146"                                                                                                                                                                                                             </td><td>"ARG" es el código para la República Argentina.

"06007" es el código de un departamento

[-58.111111, -35.111111, -57.111111, -33.111111] es un bounding box

[-58.111111, -35.111111] es un punto geográfico

"http://sws.geonames.org/6255146"                                                                                                                                                                                                                                                                                            </td><td>spatial    </td><td>String</td></tr>
</tbody>
</table>

## Tema (theme)

<table class="docutils">
<thead>
<tr><th>Nombre       </th><th>Requerido  </th><th>Descripción                              </th><th>Ejemplo                                                                                                            </th><th>Variable   </th><th>Tipo  </th></tr>
</thead>
<tbody>
<tr><td>Identificador</td><td>R          </td><td>El identificador del tema.               </td><td>AGRI                                                                                                               </td><td>id         </td><td>String</td></tr>
<tr><td>Título       </td><td>R          </td><td>La etiqueta o título de un tema.         </td><td>Agricultura, pesca, silvicultura y alimentación                                                                    </td><td>label      </td><td>String</td></tr>
<tr><td>Descripción  </td><td>R          </td><td>Una breve y concisa descripción del tema.</td><td>Bajo este concepto se incluyen datasets que cubren dominios tales como agricultura, pesca, forestación o alimentos.</td><td>description</td><td>String</td></tr>
</tbody>
</table>

# ANEXOS

## Anexo I - Taxonomía temática (tabla)
El Perfil Regional de Metadatos propone el uso de la taxonomía temática definida por la Unión Europea.

<table class="docutils">
  <colgroup>
    <col style="width:33%">
    <col style="width:33%">
    <col style="width:33%">
  </colgroup>
  <tbody>
    <tr>
      <td>Código (authority code)</td>
      <td>Etiqueta (label)</td>
      <td>Descripción (description)</td>
    </tr>
    <tr>
      <td>AGRI</td>
      <td>Agroganadería, pesca y forestación</td>
      <td>Datos referidos a agroganadería, pesca y forestación. Por ejemplo: 'Lechería: precio pagado al productor' o 'Superficie forestada'.</td>
    </tr>
    <tr>
      <td>ECON</td>
      <td>Economía y finanzas</td>
      <td>Datos referidos a economía y finanzas. Por ejemplo: 'Deuda pública'.</td>
    </tr>
    <tr>
      <td>EDUC</td>
      <td>Educación, cultura y deportes</td>
      <td>Datos referidos a educación, cultura y deportes. Por ejemplo: 'Registro de Establecimientos Educativos'.</td>
    </tr>
    <tr>
      <td>ENER</td>
      <td>Energía</td>
      <td>Datos referidos a energía. Por ejemplo: 'Productos mineros exportados' o 'Precios del GNC'.</td>
    </tr>
    <tr>
      <td>ENVI</td>
      <td>Medio ambiente</td>
      <td>Datos referidos a medio ambiente. Por ejemplo: 'Operadores de residuos peligrosos'.</td>
    </tr>
    <tr>
      <td>GOVE</td>
      <td>Gobierno y sector público</td>
      <td>Datos referidos a gobierno y sector público. Por ejemplo: 'Inmuebles del estado Nacional'.</td>
    </tr>
    <tr>
      <td>HEAL</td>
      <td>Salud</td>
      <td>Datos referidos a salud. Por ejemplo: 'Estadísticas nacionales de VIH/SIDA'.</td>
    </tr>
    <tr>
      <td>INTR</td>
      <td>Asuntos internacionales</td>
      <td>Datos referidos a asuntos internacionales. Por ejemplo: 'Representaciones argentinas en el exterior'.</td>
    </tr>
    <tr>
      <td>JUST</td>
      <td>Justicia, seguridad y legales</td>
      <td>Datos referidos a justicia, seguridad y legales. Por ejemplo: 'Censo penitenciario'.</td>
    </tr>
    <tr>
      <td>REGI</td>
      <td>Regiones y ciudades</td>
      <td>Datos referidos a regiones y ciudades. Por ejemplo: 'Departamentos de la provincia de Río Negro'.</td>
    </tr>
    <tr>
      <td>SOCI</td>
      <td>Población y sociedad</td>
      <td>Datos referidos a población y sociedad. Por ejemplo: 'Turistas residentes que viajan por Argentina'.</td>
    </tr>
    <tr>
      <td>TECH</td>
      <td>Ciencia y tecnología</td>
      <td>Datos referidos a ciencia y tecnología. Por ejemplo: 'Recursos humanos en ciencia y tecnología'.</td>
    </tr>
    <tr>
      <td>TRAN</td>
      <td>Transporte</td>
      <td>Datos referidos a transporte. Por ejemplo: 'Estadísticas viales'.</td>
    </tr>
    </tbody>
</table>

## Anexo II - Taxonomía temática (JSON)

Esta es la taxonomía temática global:
<pre><code class="json hljs">[
    {
        "<span class="hljs-attribute">id</span>":<span class="hljs-value"><span class="hljs-string">"AGRI"</span></span>,
        "<span class="hljs-attribute">label</span>":<span class="hljs-value"><span class="hljs-string">"Agroganadería, pesca y forestación"</span></span>,
        "<span class="hljs-attribute">description</span>":<span class="hljs-value"><span class="hljs-string">"Datos referidos a agroganadería, pesca y forestación. Por ejemplo: 'Lechería: precio pagado al productor' o 'Superficie forestada'."</span>
    </span>},
    {
        "<span class="hljs-attribute">id</span>":<span class="hljs-value"><span class="hljs-string">"ECON"</span></span>,
        "<span class="hljs-attribute">label</span>":<span class="hljs-value"><span class="hljs-string">"Economía y finanzas"</span></span>,
        "<span class="hljs-attribute">description</span>":<span class="hljs-value"><span class="hljs-string">"Datos referidos a economía y finanzas. Por ejemplo: 'Deuda pública'."</span>
    </span>},
    {
        "<span class="hljs-attribute">id</span>":<span class="hljs-value"><span class="hljs-string">"EDUC"</span></span>,
        "<span class="hljs-attribute">label</span>":<span class="hljs-value"><span class="hljs-string">"Educación, cultura y deportes"</span></span>,
        "<span class="hljs-attribute">description</span>":<span class="hljs-value"><span class="hljs-string">"Datos referidos a educación, cultura y deportes. Por ejemplo: 'Registro de Establecimientos Educativos'."</span>
    </span>},
    {
        "<span class="hljs-attribute">id</span>":<span class="hljs-value"><span class="hljs-string">"ENER"</span></span>,
        "<span class="hljs-attribute">label</span>":<span class="hljs-value"><span class="hljs-string">"Energía"</span></span>,
        "<span class="hljs-attribute">description</span>":<span class="hljs-value"><span class="hljs-string">"Datos referidos a energía. Por ejemplo: 'Productos mineros exportados' o 'Precios del GNC'."</span>
    </span>},
    {
        "<span class="hljs-attribute">id</span>":<span class="hljs-value"><span class="hljs-string">"ENVI"</span></span>,
        "<span class="hljs-attribute">label</span>":<span class="hljs-value"><span class="hljs-string">"Medio ambiente"</span></span>,
        "<span class="hljs-attribute">description</span>":<span class="hljs-value"><span class="hljs-string">"Datos referidos a medio ambiente. Por ejemplo: 'Operadores de residuos peligrosos'."</span>
    </span>},
    {
        "<span class="hljs-attribute">id</span>":<span class="hljs-value"><span class="hljs-string">"GOVE"</span></span>,
        "<span class="hljs-attribute">label</span>":<span class="hljs-value"><span class="hljs-string">"Gobierno y sector público"</span></span>,
        "<span class="hljs-attribute">description</span>":<span class="hljs-value"><span class="hljs-string">"Datos referidos a gobierno y sector público. Por ejemplo: 'Inmuebles del estado Nacional'."</span>
    </span>},
    {
        "<span class="hljs-attribute">id</span>":<span class="hljs-value"><span class="hljs-string">"HEAL"</span></span>,
        "<span class="hljs-attribute">label</span>":<span class="hljs-value"><span class="hljs-string">"Salud"</span></span>,
        "<span class="hljs-attribute">description</span>":<span class="hljs-value"><span class="hljs-string">"Datos referidos a salud. Por ejemplo: 'Estadísticas nacionales de VIH/SIDA'."</span>
    </span>},
    {
        "<span class="hljs-attribute">id</span>":<span class="hljs-value"><span class="hljs-string">"INTR"</span></span>,
        "<span class="hljs-attribute">label</span>":<span class="hljs-value"><span class="hljs-string">"Asuntos internacionales"</span></span>,
        "<span class="hljs-attribute">description</span>":<span class="hljs-value"><span class="hljs-string">"Datos referidos a asuntos internacionales. Por ejemplo: 'Representaciones argentinas en el exterior'."</span>
    </span>},
    {
        "<span class="hljs-attribute">id</span>":<span class="hljs-value"><span class="hljs-string">"JUST"</span></span>,
        "<span class="hljs-attribute">label</span>":<span class="hljs-value"><span class="hljs-string">"Justicia, seguridad y legales"</span></span>,
        "<span class="hljs-attribute">description</span>":<span class="hljs-value"><span class="hljs-string">"Datos referidos a justicia, seguridad y legales. Por ejemplo: 'Censo penitenciario'."</span>
    </span>},
    {
        "<span class="hljs-attribute">id</span>":<span class="hljs-value"><span class="hljs-string">"REGI"</span></span>,
        "<span class="hljs-attribute">label</span>":<span class="hljs-value"><span class="hljs-string">"Regiones y ciudades"</span></span>,
        "<span class="hljs-attribute">description</span>":<span class="hljs-value"><span class="hljs-string">"Datos referidos a regiones y ciudades. Por ejemplo: 'Departamentos de la provincia de Río Negro'."</span>
    </span>},
    {
        "<span class="hljs-attribute">id</span>":<span class="hljs-value"><span class="hljs-string">"SOCI"</span></span>,
        "<span class="hljs-attribute">label</span>":<span class="hljs-value"><span class="hljs-string">"Población y sociedad"</span></span>,
        "<span class="hljs-attribute">description</span>":<span class="hljs-value"><span class="hljs-string">"Datos referidos a población y sociedad. Por ejemplo: 'Turistas residentes que viajan por Argentina'."</span>
    </span>},
    {
        "<span class="hljs-attribute">id</span>":<span class="hljs-value"><span class="hljs-string">"TECH"</span></span>,
        "<span class="hljs-attribute">label</span>":<span class="hljs-value"><span class="hljs-string">"Ciencia y tecnología"</span></span>,
        "<span class="hljs-attribute">description</span>":<span class="hljs-value"><span class="hljs-string">"Datos referidos a ciencia y tecnología. Por ejemplo: 'Recursos humanos en ciencia y tecnología'."</span>
    </span>},
    {
        "<span class="hljs-attribute">id</span>":<span class="hljs-value"><span class="hljs-string">"TRAN"</span></span>,
        "<span class="hljs-attribute">label</span>":<span class="hljs-value"><span class="hljs-string">"Transporte"</span></span>,
        "<span class="hljs-attribute">description</span>":<span class="hljs-value"><span class="hljs-string">"Datos referidos a transporte. Por ejemplo: 'Estadísticas viales'."</span>
    </span>}
]
</code></pre>

## Anexo III - Pautas para la selección de etiquetas

Elegir buenas etiquetas hace más fácil la búsqueda de datasets para los usuarios. Cuanto más amplia y uniforme sea la lista de etiquetas, mayor será su efectividad.

Estas son pautas para definir etiquetas aplicables a la propiedad keyword de la clase dataset:

- Escribir correctamente y en plural.
- Usar mayúsculas sólo donde corresponda.
- Identificar palabras claves.
- Respetar la existencia de etiquetas anteriores.
- Agregar sinónimos y emplear lenguaje natural.
- Usar una sóla palabra. Si es muy necesario, usar más de una.
- Si la etiqueta tiene más de una palabra, debe estar separada por un espacio, ej: "declaraciones juradas".

Preguntas útiles a la hora de pensar los etiquetas:

- ¿Cuál es el tema?
- ¿Qué aspectos serán de interés para los usuarios?
- ¿De qué otro modo buscaría sobre esta información?
- ¿De qué tipo de información se trata?
- ¿Qué área la provee?

## Anexo IV - Especificación de frecuencias (según ISO-8601)

<table class="docutils">
  <tbody><tr>
    <td>Frecuencia</td>
    <td>Valor según ISO-8601</td>
  </tr>
  <tr>
    <td>Cada diez años</td>
    <td>R/P10Y</td>
  </tr>
  <tr>
    <td>Cada cuatro años</td>
    <td>R/P4Y</td>
  </tr>
  <tr>
    <td>Cada tres años</td>
    <td>R/P3Y</td>
  </tr>
  <tr>
    <td>Cada dos años</td>
    <td>R/P2Y</td>
  </tr>
  <tr>
    <td>Anualmente</td>
    <td>R/P1Y</td>
  </tr>
  <tr>
    <td>Cada medio año</td>
    <td>R/P6M</td>
  </tr>
  <tr>
    <td>Cuatrimestralmente</td>
    <td>R/P4M</td>
  </tr>
  <tr>
    <td>Trimestralmente</td>
    <td>R/P3M</td>
  </tr>
  <tr>
    <td>Bimestralmente</td>
    <td>R/P2M</td>
  </tr>
  <tr>
    <td>Mensualmente</td>
    <td>R/P1M</td>
  </tr>
  <tr>
    <td>Cada 15 días</td>
    <td>R/P0.5M</td>
  </tr>
  <tr>
    <td>Tres veces por mes</td>
    <td>R/P0.33M</td>
  </tr>
  <tr>
    <td>Semanalmente</td>
    <td>R/P1W</td>
  </tr>
  <tr>
    <td>Dos veces a la semana</td>
    <td>R/P0.5W</td>
  </tr>
  <tr>
    <td>Tres veces a la semana</td>
    <td>R/P0.33W</td>
  </tr>
  <tr>
    <td>Diariamente</td>
    <td>R/P1D</td>
  </tr>
  <tr>
    <td>Cada hora</td>
    <td>R/PT1H</td>
  </tr>
  <tr>
    <td>Continuamente actualizado</td>
    <td>R/PT1S</td>
  </tr>
  <tr>
    <td>Eventual</td>
    <td>eventual</td>
  </tr>
</tbody></table>


