# MapBdVistas
Sistema de automatización de generación de código desde bases de datos sqlite a clases para Gambas3 siguiendo el patrón de diseño VO - DAO.


Realizado en Gambas3 para Gnu/Linux

![Gambas3 Logo](gambas.png)
![MapBdVistas Logo](iconobd.png)

Autor: Julio Sánchez Berro


Enlace a documentación online [Blog MapBdVistas](http://mapbdvistas.blogspot.com/p/documentacion.html)


## **_Comentarios de Versiones_**

0.2.99920: 11/03/2016

**bug:** error en el formulario de resumen final, no buscaba el
directorio user.home sino “home/minino”

**mejora:** en el formulario final, si se han producido 0 lineas o 0
clases, se indica con un mensaje de error en la parte superior.

0.2.99919: 11/03/2016

**Cambios:** el programa se instala ahora en el menu /programacion con
el nombre “MapBdVistas”

**Mejoras:** Admite la definicion de las tablas en varias lineas.

0.2..99918: Corregido bug cuando se intentaba redibujar un gridviews con
pictures dentro.

Sustituyo las lineas:

-   gridviewPropio.rows.count = 0

por

-   gridviewPropio.clear()

0.2.99916: Corregido en más lineas el error de 0.2.99915. Ademas añado a
los &1 los apostrofes quedando ‘&1’

0.2.99915: Corregido Bug en buscar por contenido

linea anterior: Try mRs = conectar.hconn.Exec(SQLString)

linea cambiada a: Try mRs = conectar.hconn.Exec(Subst(SQLString, valor))

0.2.99913: Se hace comprobacion al escribir numeros o fechas y si da
error de que son cadenas, los convierte en número para mostrarlos

0.2.99912: Se añade VARCHAR a los tipos de campos reconocidos. Los tipos
de campos reconocidos son:

> **"DATETIME" …..** como "Date"
>
> **"BOOL" ……** como "Boolean"
>
> **"TEXT"** **……** como "String"
>
> **“VARCHAR"** **……** como "String"
>
> **"INTEGER PRIMARY KEY" ……** como "Null" ‘campo autonumerico
>
> "**INTEGER PRIMARY KEY AUTOINCREMENT NOT NULL**" **……** como "Null"
> ‘campo autonumerico
>
> **"INT4 NOT NULL**" **……** como "Null" ‘campo autonumerico
>
> **"INTEGER PRIMARY KEY AUTOINCREMENT NULL"** **……** como "Null" ‘campo
> autonumerico
>
> **"INTEGER PRIMARY KEY AUTOINCREMENT NOT NULL UNIQUE"** **……** como
> "Null" ‘campo autonumerico
>
> **"NUMERIC"** **……** como "float"
>
> **"INT4" ……** como "INTEGER"
>
> **"FLOAT8"……** como "float"

0.2.99911: Se añade el botón de Update, para que informe si existe
alguna version en el servidor nueva.

Bug: Se pone a las variable de colorfilaimpar y colorfilapar, valores
iniciales para que no salgan en negro. Ahora salen en blanco y cyan.

0.2.999.10: Añadido al formulario Automatico, una comprobacion que hace
que se quiten los espacios finales en los textbox, para que luego no de
problemas si usamos los datos para rellenar combobox.

0.2.999.09 Revisado algunos preocedimiento de busqueda que usaban
comillas y cadenas , y los he ambiado a susbituciones por
hconn.Exec(..).

0.2.99908 Funcion ExtraerRegistro mejorada

- si no puede extraer un registro, devuelve null y muesta un mensaje en
consola

0.2.99907 funcion que devuelve si una columna es del tipo ID o no

me.NoesTipoId(nombre del campo) as boolean

Usada para formartar o no la columna que contiene datos tipo ID

0.2.99906: Modificaciones por problemas en . y , decimal

- Los campos ID, no los formateo, para que no haya problemas con la
conversion a numerico

- filaseleccionadaVO() corregido bug al leer gridview columna 0,
convierte el numero (pero antes cambia el . por la ,

0.2.99905 Añadido funcion:

-&gt; **UltimoIntroducido()**, que devuelve el objeto VO ultimo
introducido de la tabla/vista

> Sustituye a las sentencias:
>
> hresult = manejadorLabores.contenido()
>
> hresult.MoveLast
>
> ArrayTmpVo = manejadorLabores.ConvertirResult(hresult)\[0\]

-&gt; SVG: Mejorado el dibujo de conexiones, con las Vistas:

Ahora las vistas se conectan a las tablas relacionadas en su definición.

0.2.99904 Añado al archivo .svg, el dibujo de las conexiones entre
tablas, (guiandome por los campos id repetidos en las tablas).

0.2.99903 .Crea archivo .svg con el esquema de tablas y vistas usadas,
incluyendo campos y tipos. He añadido que cree el archivo .tar.gz de la
base de datos.

0.2.99902 Creo una nueva variable en las clase DAO:

-   public **ocultaId** as string

Si su valor es igual a “id” o “”: las columnas que tengan de nombre “id”
, no se veran

Si su valor es igual a “id\*”: las columnas cuyo nombre empiezen por id,
no se veran

En el resto de casos, se muestra la columna del gridview.

**Nota:**

Si es la ultima columna, no se aplica. Hay que cambiar, el orden de las
columnas, para que la ultima siempre se deba de mostrar.

0.2.9901 Las clases VO, tienen la funcion copia, que devuelve una copia
de una clase dada o de si misma.

PUBLIC FUNCTION **Copia**(Optional dato as xxVO) as xxVO

0.2.999 Si la vista viene definida usando \* , no es posible identificar
los campos a mostrar, y no es posible usarla en el mapdbvistas. Se
muestra un mensaje indicando que no se crearán clases DAO ni VO para esa
vista.

0.2.998 Resuelto problemas con el editor de gambas3 de bases de datos
con los nombres de las tablas y campos y tipos de datos, ya que les
añadir comillas simple y cambia los tipos integer por int4 o float por
float8

0.2.997. Propiedades de VO, las he puesto en minusculas (son los nombres
de los campos)0

0.2.996 Modificacion para las columnas cuyo campo empieza por ID no se
vean (ancho 0)

0.2.995 -Añadido que en las columnas que tengamos numeros, se aplique el
formato ",\#.\#0"

Corregido un bug en la version 0.2.993, faltaba definir una variable que
le habia anulado al poner un comentario delante.

0.2.994 - Añado enlace a la pagina web del proyecto:
http://mapbdvistas.blogspot.com.es/

0.2.993- Añadido en clases DAO. funcion copia, que devuelve una copia de
la clase VO dada

0.2.992- Corregido un problema con el sistema de formularios
Automatizados. Cuando se usaba un textarea, y se introducia vairas
lineas, al editar el registro, fallaba la presentacion de los campos.

0.2.99: - EXTRAER DATO DE UN REGISTRO añado funcion para extraer un
registro dado un el numero del id y el nombre del campos de la TABLA
function **ExtraerRegistro**(NombreCampo as string,id as integer)

Lo que se pretende sustituir es este tipo de codigo es:

tmpVO1 =
tmpDAO.ConvertirResult(manejadorSubcategoriaAux.BuscarIgualIdsubcategoria(tmpVO.id))\[0\]

**por:**

tmpVO1 = tmpDAO.ExtraeRegistro(“Idsubcategoria”,tmpVO.id) ‘extraigo el
1º registro de la tabla/vista que coincida con el id.

![dado nombre de campo y valor del campo devuelver
registro.png](media/image1.png){width="6.5in"
height="3.6527777777777777in"}

“dado el nombre del campo “iddescomuesto”, y el valor “10” (de ese
campo), devuelve el primer registro que cumpla esa condicion), el
registro sombreado en amarillo ( 10/2/hora/Pintado Piscina/1000/0/0)”

0.2.98: Borrado de la carpeta home/usuario/temporal al inicio, para no
mezclar proyectos

Añadido formulario final, con resumen del numero de lineas creados y
ficheros creados.

Tambien se añade un archivo llamado “EstructuraBD.txt” con la decripcion
(schema) de tablas, vistas, campos de la base de datos analizada.

0.2.97. Mensaje de waring cuando no se encuentra un nombre de un campo
en el gridview

try
datocontenido=me.hresultadoNuevo\[replace(me.gridviewPropio.columns\[column\].text,"\_",".")\]

if error then

print "warning !!: nombre de campo que no encuentro "&
me.GridViewPropio.tag\[column\] & " en la tabla/vista"

endif

Nota: del waring

Puede ser motivado, porque hemos quitado intenciondamente una campo que
no queremos mostrar.

Notas: Renombrar nombres compuestos de la base de datos (tablas y/o
vistas):

Los campos de la base de datos (tanto tablas o vistas), deben de usar
“alias”, para evitar problemas con los nombre compuestos “nombretabla
punto nombre campo”

Notas: Vistas

Siempre se debe poner el campo ID del registro (y el que usemos para
referirnos a una Tabla Principal de donde sale una Vista,), en primer
lugar, para poder tomar los datos del id, al hacer click en el gridview.

0.2.95: eliminado del formulario del programa, la opción de informe. No
era completo, y para dejar una cosa a medias la he quitado.

0.2.94: modificado el formulario Automatico para que acepte un nuevo
valor opcional en los valuebox, cuando se ponga 2, se oculta el
valuebox.

Con valor True: se queda en *modo solo lectura*

codigocampos &= "valuebox|iddescompuestomateriales|" &
("iddescompuestomateriales") & "|0|**TRUE**;"

Oculta el campo para que *no se vea*: **2**

codigocampos &= "valuebox|iddescompuestomateriales|" &
("iddescompuestomateriales") & "|0|**2**;"

0.2.93 Se añade el comun.modulo con funciones comunes usadas para el
cambio de formularios automatizados.

0.2.92: Si se define un Alias de un campo se admite que este entre
comillas dobles o simples:

> CREATE VIEW "VistaSubcategoria" AS select idsubcategoria as
> 'id',textocapitulo,textosubcategoria from subcategoria,categoria where
> subcategoria.idcapitulo=categoria.idcategoria

0.2.91: corregido linea que muestra dato de fecha en Observador\_data()

If IsDate(Str\$(datocontenido)) Then

Me.gridviewPropio.Data.text = Format(Date(datocontenido),
Me.formatofecha)

0.2.9:

Corregido problemas al detectar el nombre y las vistas de la base de
dato Cortes

0.2.8:

Mejorado el sistema de presentación de gridview Horizontales.

Nuevo metodo:

PUBLIC FUNCTION mostrarRegistroVO(objetoVO As VO, grid AS GridView) AS
Result" -&gt; para el gridview definido como datos horizotnales (1
registro mostrado)

Resuelto ancho del grid Horizontal de datos, para que se muestren con el
ancho adecuado.

0.2.7. Cambio de la forma de calculo del ancho de las columnas, ya que
antes daba problemas con las version 3.6.X.

Se ha creado una variable publica, que indica el ancho de las columnas.

'Array que contiene los valores del ancho de las columnas.

Public arrayAnchoColumnas As New Integer\[\]
