## Aspectos técnicos del proceso


### Proceso de traducción

Cada archivo original de traducción (.csv) se ha convertido a un formato
de hoja de cálculo OpenDocument (.ods) para facilitar su edición. Se
agregaron dos columnas: una al inicio para mantener el número de renglón
original (para poder reordenar los registros según sea más conveniente
y mantener la posibilidad de regresar al ordenamiento original); y una
columna al final donde se copian las cadenas de las traducciones
originales de las cadenas que han sido cambiadas.

Una idea para realizar la edición de la traducción es la siguiente.

Deben mantenerse abiertos los siguientes elementos:

- El sistema Frappé + ERPNext en alguna ventana de navegador (browser).
- Editor de código (p.ej. Sublime Text), con acceso a todo el árbol del
  código del proyecto (normalmente en `~/frappe-bench`).
- Hoja de cálculo (p.ej. LibreOffice Calc) con el archivo .ods en
  edición.
- Este archivo (`notas.md`).

La traducción se debe editar en el archivo .ods mientras se buscan
referencias contextuales en la aplicación (navegador) y/o código fuente.
El archivo de hoja de cálculo puede ordenarse por la 2a. columna (que
contiene la referencia de origen de la cadena a traducir) para
facilitar la traducción de secciones similares (p.ej. de un mismo
formulario o DocType).

Es conveniente tomar nota de cualquier decisión o nomenclatura que se
establezca durante la traducción para mantener una consistencia de
la edición de la misma; para eso se puede utilizar este archivo de notas
en las secciones posteriores de este documento
([Consideraciones](#consideraciones-generales) y
[Vocabulario](#vocabulario-establecido)).


### Pruebas de traducción generada

Nota: Debería buscarse la manera de automatizar la generación de los
archivos de salida correspondientes (`es-MX.csv`) mediante algún
script en Python.

---

## Observaciones de la traducción


### Consideraciones generales

- El establecimiento del [vocabulario establecido](#vocabulario-establecido)
  debe ser un lineamiento general de las traducciones; sin embargo, no debería
  tratarse como una regla estricta para generar las traducciones; es decir: en
  algunas situaciones es probable que puedan usarse sinónimos para
  evitar la monotonía del texto. Como ejemplo de lo anterior tenemos la
  siguiente frase: "Permission at level 0 must be *set* before higher levels
  are *set*", la cual puede traducirse así: "Los permisos de nivel 0 deben
  *establecerse* antes de *definir* niveles más altos". La palabra "set" se
  traduce en la frase como "establecerse" y "definirse" (sinónimo), a pesar
  de que el vocabulario la define como "establecer".

- Debe evitarse utilizar mayúsculas iniciales en la medida de lo posible;
  a menos que se trate de términos estándares o técnicos (p.ej. DocType,
  Javascript).

- En las descripciones de item en los archivos de configuración de módulos
  (métodos `get_data()`) se dejarán con punto al final. En las descripciones
  originales ( en inglés) tienen mezcladas las dos formas.

- En los mensajes de error o excepción (lanzados mediante `frappe.throw()`)
  se manejarán sin punto final. En los mensajes originales están mezcladas
  las dos formas.


### Vocabulario establecido

- Log = registro
- Desk = escritorio
- Request = solicitud
- Field = campo
- DocType = DocType
- Script = script
- Background = segundo plano
- Developer = desarrollador
- Set = establecer / definir
- Bulk = masivo/a
- Item = elemento / artículo / registro
- Upload = cargar
- Add = añadir
- Manage = administrar
- Setup = configurar
- Default = por defecto
- Workflow = flujo de trabajo
- Role = rol
- Check = verificar
- Report = reporte
- Settings = configuración
- Scheduler = planificador
- Child = dependiente
- Sorry = lo sentimos
- Login, logged in = inicio de sesión, iniciar sesión
- Find = localizar
- Everyone = todos
- Serie = secuencia, secuencias
- Merge = fusionar
- Row = renglón
- Fieldname = nombre del campo
- Link = enlace
- Currency = moneda
- Check (sustantivo) = Verificación
- Fieldtype = tipo de campo
- Fold = repliegue
- Form = formulario
- Pattern = patrón
- Enter = ingresar
- Read = leer
- Write = escribir
- Create = crear
- Delete = borrar
- Submit = aprobar
- Cancel = cancelar
- Amend = corregir
- Report (permiso) = generar reporte
- Export = exportar
- Import = importar
- Share = compartir
- Print = imprimir
- Email (permiso) = enviar por email
- Folder = carpeta
- Mandatory = obligatorio
- Home (file list) = inicio
- Attachments (file list) = adjuntos
- Administrator (user) = usuario administrador
- Disable = deshabilitar
- Enable = habilitar
- Script = script
- Post = publicación
- Refresh = actualizar


### Observaciones de archivos de origen (bugs, inconsistencias)

#### Notas generales

- Existen cadenas que no han sido integradas a los archivos .csv
  pero sí se generan en los archivos de código (llaman a la función de
  traducción de frappé: `frappe._()`). Después de traducir los archivos
  originales, deben buscarse dichas cadenas; es probable que exista un
  proceso (script) automatizado para hacer tal cosa.

- Algunas secciones se refieren a cadenas integradas en archivos
  de código correspondientes a pruebas unitarias. Es probable que
  dichas pruebas no se comporten correctamente, porque aparentemente
  no se tuvo el cuidado de usar la función de traducción de frappé
  en todas esas cadenas; por lo que las llamadas a las funciones de
  prueba (`Assert`) podrían retornar valores inválidos.


#### App Frappé (`apps/frappe/translations/es.csv`)

- Casi todas las cadenas para `apps/frappe/frappe/config/website.py` tienen
  mal definido el número de línea al que hacen referencia en el archivo
  de código correspondiente (`website.py`).

- No existe la entrada `apps/frappe/frappe/core/doctype/doctype/doctype.py +478`.
  La cadena original dice: "Apply User Permissions".

