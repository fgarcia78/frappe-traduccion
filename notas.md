### Aspectos técnicos del proceso


## Proceso de traducción

Cada archivo original de traducción (.csv) se ha convertido a un formato
de hoja de cálculo OpenDocument (.ods) para facilitar su edición. Se
agregaron dos columnas: una al inicio para mantener el número de renglón
original (para poder reordenar los registros según sea más conveniente
y mantener la posibilidad de regresar al ordenamiento original); y una
columna al final donde se copian las cadenas de las traducciones
originales de las cadenas que han sido cambiadas.

Una idea para realizar la edición de la traducción es la siguiente.
Mantener abiertos los siguientes elementos:

- El sistema Frappé + ERPNext en alguna ventana de navegador (browser).
- Editor de código (p.ej. Sublime Text), con acceso a todo el árbol del
  código del proyecto (normalmente en `~/frappe-bench`).
- Hoja de cálculo (p.ej. LibreOffice Calc) con el archivo .ods en
  edición.
- Este archivo (`notas.md`).

La traducción se debe editar en el archivo .ods, mientras se buscan
referencias contextuales en la aplicación y/o código fuente. Además,
es conveniente tomar nota de cualquier decisión o nomenclatura que se
establezca durante la traducción para mantener una consistencia de
la edición de la misma; para eso se puede utilizar este archivo de notas
en las secciones posteriores (Consideraciones y Vocabulario).


## Pruebas de traducción generada

Por definir...

---

### Observaciones de la traducción


## Consideraciones generales

- Debe evitarse utilizar mayúsculas iniciales en la medida de lo posible;
  a menos que se trate de términos estándares o técnicos (p.ej. DocType,
  Javascript).

- En las descripciones de item en los archivos de configuración de módulos
  (métodos `get_data()`) se dejarán con punto al final. En las descripciones
  originales ( en inglés) tienen mezcladas las dos formas.


## Vocabulario establecido

- Log = registro
- Desk = escritorio
- Request = solicitud
- Field = campo
- DocType = DocType
- Script = script
- Background = segundo plano
- Developer = desarrollador
- Set = establecer
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

