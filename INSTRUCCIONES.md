# Llamador de pacientes · Centro de Salud Aguas Blancas — Instalación

Dos piezas. En la misma red funcionan sin internet; desde otra red o con otro internet se conectan por internet, cifrado (ver sección 5):

- **LlamadorTV-AguasBlancas.apk** → se instala en el Smart TV Android de la sala de espera. Pesa menos de 1 MB: las 13 voces latinas se descargan solas la primera vez que se abre (ver paso 5).
- **Extension-Llamador-AguasBlancas.zip** → se instala en Chrome en cada PC de consultorio.

Cuando el profesional toca el **parlante** (Llamar Paciente) en el panel de consultorio del **Registro de Enfermería** o en la **Estación de Trabajo de Odontología**, el TV muestra el nombre del paciente y el consultorio, toca un timbre y lo anuncia dos veces (por ejemplo: "Salto Mercedes, consultorio 3"). En la red local los datos no salen del centro; por internet viajan cifrados.

**En el TV:** arriba al centro se lee "Centro de Salud Aguas Blancas". Cada llamado queda en pantalla **1 minuto** (una barra verde muestra el tiempo que le queda) y después desaparece; el TV vuelve a la bienvenida con consejos de salud. Los nombres no se guardan en el TV.

---

## 1. TV (una sola vez)

1. Copiá `LlamadorTV-AguasBlancas.apk` a un pendrive y conectalo al TV (o usá una app tipo "Send Files to TV").
2. En el TV: **Ajustes › Seguridad › Fuentes desconocidas** (o "Instalar apps desconocidas") y habilitá el administrador de archivos que vayas a usar.
3. Abrí el APK desde el administrador de archivos e instalalo.
4. Abrí **Llamador Aguas Blancas**. Abajo a la derecha aparece la dirección, por ejemplo `192.168.1.50:8765`. **Anotala.**
5. **Voces:** la primera vez, el TV descarga solo las voces latinas y el motor de voz (unos 420 MB de internet; ocupan unos 390 MB en el TV). Abajo a la derecha se ve el avance, por ejemplo "Descargando voces latinas: Claudia (2 de 5): 45 %". Primero llegan las más rápidas (Claudia y Alejandro), después Sofía, Mateo y las demás, y al final Daniela. Cada voz se puede usar apenas termina de bajar; mientras tanto los llamados se anuncian igual, con una voz parecida o con la voz del TV. Si se corta internet o falta espacio, lo reintenta solo. Se hace una sola vez: al actualizar la app las voces quedan.
6. Recomendado:
   - Pedile al área de sistemas que le **reserve esa IP** al TV en el router (si cambia, hay que reconfigurar las PCs).
   - Desactivá el protector de pantalla / modo ahorro del TV.

Prueba rápida: desde un celular conectado al mismo WiFi, abrí `http://IP-DEL-TV:8765` y tocá "Enviar al TV".

## 2. Cada PC de consultorio

1. Descomprimí `Extension-Llamador-AguasBlancas.zip` en una carpeta fija (por ejemplo `C:\LlamadorTV`). **No la borres** después.
2. En Chrome abrí `chrome://extensions`, activá **Modo de desarrollador** (arriba a la derecha) y tocá **Cargar descomprimida**. Elegí la carpeta.
3. Se abre la configuración:
   - **Número de consultorio**: ej. `3`.
   - **Dirección del TV en la red local**: la que anotaste (si esta PC está en otra red, dejala vacía y usá el código, sección 5).
   - Tocá **Probar conexión** (Chrome pide permiso para hablar con el TV: aceptá).
   - **Voz del llamado**: aparecen todas las voces en tarjetas, femeninas a la izquierda y masculinas a la derecha. Tocá **▶** para escuchar cada una en la PC y tocá la tarjeta para elegirla (se guarda sola). Después tocá **Escuchar en el TV** (dice "María Fernanda Gutiérrez, consultorio …"). Las voces son de la app del TV (se descargan solas la primera vez), son latinas y después funcionan sin internet:
     - Femeninas: **Daniela** (Argentina), **Claudia** (México), Sofía, Lucía, Valentina, Camila y Julieta (latino neutro).
     - Masculinas: **Alejandro** (México), Mateo, Diego, Martín, Tomás y Joaquín (latino neutro).
     - **Alejandro y Claudia son las más rápidas** (el nombre sale apenas termina el timbre aun en TVs lentos).
     - Con "Automática" cada consultorio usa una voz distinta, alternando mujer y hombre (1 → Daniela, 2 → Alejandro, 3 → Claudia, 4 → Mateo…). En la tarjeta "Automática" dice qué voz le toca.
4. Recargá el panel con F5 (Registro de Enfermería u Odontología, el que use esa PC).

Listo: al tocar el parlante aparece abajo a la derecha "Llamado enviado al TV". Si sale en rojo, dice por qué (TV apagado, dirección mal escrita, etc.).

**Velocidad del llamado:**
- Mientras el panel está abierto, la extensión deja lista la conexión con el TV: en la red local el llamado llega en milésimas de segundo y el TV muestra el nombre al instante.
- **El TV prepara de antemano los nombres de todos los pacientes que se ven en el panel** (y de los que van apareciendo), y también el del paciente sobre cuyo parlante el médico apoya el mouse. Al hacer clic, toca un timbre corto (menos de medio segundo) y dice el nombre enseguida, sin tener que generarlo en ese momento. El TV no muestra esos nombres ni los guarda en su memoria permanente: los tiene en la memoria de trabajo como mucho 30 minutos.
- "Consultorio N" queda guardado en el TV para cada voz, así solo hay que preparar el nombre.
- Un llamado siempre pasa primero: si está sonando un aviso para la sala, se corta.
- Si la PC tiene la dirección y el código, el llamado sale por la red local y, si no hay respuesta inmediata, también por internet: el TV lo anuncia una sola vez.

**Horario de atención en el TV:** pestaña **Horario de atención** de la extensión (también desde el ícono › **Horarios**). Es una sola lista para todo el centro y se guarda en el TV, así que se ve y se cambia desde cualquier PC. **Para que se vean las fotos, el TV tiene que tener la app 2.9 o más nueva** (ver sección 6).
1. Tocá **+ Agregar profesional** y completá **Profesional** (por ejemplo "Dra. Sánchez"), **Especialidad** y **Consultorio N.º**.
2. **Foto (opcional):** tocá el recuadro «Agregar foto» de la tarjeta.
   - Vienen incluidas dos ilustraciones: **Dra. Sánchez** (Clínica médica) y **Dra. Leila Civila** (Odontología). Si el nombre que escribís las incluye («Sánchez» o «Civila», con o sin tilde y en mayúsculas o minúsculas), aparece el botón **Usar la de …**: un toque y queda puesta.
   - También se puede **elegir una imagen de la PC** (PNG, JPG o WebP). La extensión la achica sola (queda en menos de 60 KB, así viaja rápido aun por internet). Una ilustración con fondo transparente se recorta justo al contorno de la persona y se ve «saliendo» de la tarjeta; una fotografía común se recorta en vertical, centrada arriba (donde suele estar la cara). Conviene una foto de frente, con buena luz y la cara grande.
   - **Cambiar** o **Quitar foto** se hacen desde la misma tarjeta. Sin foto, el TV muestra un círculo con las iniciales.
3. **Mañana** y **Tarde** tienen cada una sus propios **días** y **horas**: marcá "Atiende a la mañana" y/o "Atiende a la tarde", escribí las horas en formato de 24 horas (por ejemplo de `14:30` a `20:00`; también vale `1430`) y tocá los días de ese turno. Ejemplo: mañana lunes, miércoles y viernes de 07:30 a 12:00, y tarde martes y jueves de 14:30 a 19:00.
4. Arriba de cada tarjeta se ve un resumen ("Consultorio 5 · Mañana: Lun, Mié, Vie 07:30 a 12:00 · Tarde: Mar, Jue 14:30 a 19:00").
5. Tocá **Guardar y mostrar en el TV**. Las fotos nuevas se suben al TV en ese momento (si alguna falla, dice de qué profesional es y no se guarda nada a medias). Si falta algo, la tarjeta se marca en rojo y dice qué corregir.

Con **Ver** se filtra por consultorio (al abrir, muestra el de esa PC). En el TV, cuando no hay llamados, aparece **"Profesionales que atienden hoy"**: una tarjeta animada por profesional, con su foto, su nombre, la especialidad, el consultorio y su horario de mañana y/o tarde; quien está atendiendo en ese momento lleva la etiqueta **«En atención»**. Con 1 o 2 profesionales las tarjetas son grandes; con 3 a 6 se acomodan en una grilla y todo se achica solo para que nada se corte.
- **De 07:00 a 08:40**: los que atienden ese día, con su horario de mañana y de tarde de ese día.
- **De 13:00 a 16:30**: solo los que atienden esa tarde.
- Fuera de esos horarios, o si nadie atiende ese día, se ve la bienvenida de siempre. Si llega un llamado, se muestra el llamado y después vuelve el horario. Si hay más de 6 profesionales, la lista cambia de página cada 12 segundos (repartidas parejo).
- Las animaciones son suaves: las tarjetas entran una tras otra, la figura «sale» de su círculo de color y flota despacio, aparecen unas chispas y de tanto en tanto un reflejo cruza cada tarjeta. Usan solo movimiento y transparencia (lo más liviano para un TV), pero no pude probarlas en un TV real: si alguno se ve entrecortado, avisame.

**Ícono de la extensión** (la cruz verde en la barra de Chrome): muestra si el TV está conectado, desde qué consultorio llama esa PC y tiene botones para probar un llamado, abrir la configuración o la publicidad. Conviene fijarlo con el ícono de pin de Chrome.

## 3. Avisos por voz en la sala

En la extensión, pestaña **Avisos por voz** (también desde el ícono de la extensión › **Avisos**). El TV dice el aviso con un "ding" suave antes y muestra el texto abajo de la pantalla.

Ya vienen dos avisos cargados, de lunes a viernes, cada 1 hora hasta las 20:00:
- **Pasillo** (voz de Daniela, a las 7:15, 8:15, 9:15…): "Estimados pacientes: los llamados se anuncian por esta pantalla. No es necesario esperar en el pasillo. Por favor, aguarden en la sala de espera, para su comodidad y la del personal. Muchas gracias."
- **Silencio** (voz de Alejandro, a las 7:45, 8:45, 9:45…): "Les pedimos, por favor, mantener silencio en la sala de espera. Muchas gracias."

En cada aviso se puede cambiar el texto (hasta 400 letras), la voz, la velocidad, cada cuánto se repite (o "Solo cuando lo pida"), el horario y los días, y si el texto se muestra en pantalla. Abajo dice las **próximas veces de hoy**. Tocá **Guardar avisos en el TV** para que tome los cambios. **Decir ahora en el TV** lo dice en el momento.

**Aviso al momento:** para algo puntual sin guardarlo (por ejemplo "El consultorio 3 retoma la atención a las 15"): escribilo y tocá **Decir ahora en el TV**.

Cómo se ordena todo:
- Un **llamado** de paciente siempre tiene prioridad. Si llega mientras suena un aviso, el aviso se corta y se repite una vez cuando terminan los llamados.
- Si hay **publicidad** a la hora del aviso, el aviso espera a que termine (hasta 10 minutos). Mientras se dice un aviso, la publicidad queda en silencio.
- El TV tiene que tener bien la **hora y la fecha** (Ajustes › Fecha y hora › automática).

## 4. Publicidad en el TV

En la extensión, abrí la pestaña **Publicidad del TV** (se puede hacer desde cualquier PC que tenga la extensión configurada).

**Dos turnos:** la publicidad está separada en **Mañana (07:00 a 13:00)** y **Tarde (14:00 a 20:00)**. Cada pestaña muestra cuántas publicidades tiene y, en cada una, las horas de ese turno. Si una publicidad también suena en el otro turno, abajo lo indica. Si alguna quedó con horas fuera de los turnos (por ejemplo, 13:30), aparece una pestaña **Fuera de turno** para corregirla.

**Agregar:**
1. Elegí el **turno** y si es un **link de YouTube** o un **video para subir** (MP4, hasta 1,5 GB, solo desde la red del TV).
2. Para YouTube: en el video, tocá **Compartir › Copiar** y en la extensión tocá **Pegar** (o Ctrl+V). Sirve cualquier link: el de «Compartir» (`youtu.be/…`), el de la barra del navegador, Shorts o transmisiones.
   - Aparece una **vista previa** con la imagen, el título y el canal, y el nombre se completa solo.
   - La extensión **verifica** si el video se puede reproducir en el TV: si el dueño no lo permite, si es privado o si ya está agregado, avisa y no lo deja agregar.
   - Si es una lista de reproducción o un canal, avisa que hay que copiar el link del video.
3. Escribí las **horas** (deben estar dentro del turno) o usá **Completar: cada 30 min / 1 hora / 2 horas**.
   - **Cada hora puede tener una sola publicidad.** Mientras escribís, debajo aparece "✓ Hora libre" o qué publicidad ya usa esa hora. El TV tampoco acepta horas repetidas.
   - **Completar** pone las horas solo. Si una hora ya tiene publicidad, la nueva va **4 minutos después** (por ejemplo, 16:00 ocupada → 16:04; si 16:04 también está ocupada → 16:08). Te avisa cuáles corrió.
   - Si escribís a mano una hora ocupada, te sugiere la próxima libre ("probá 16:04").
   - Si la publicidad anterior dura más de 4 minutos, la siguiente **espera en fila** a que termine y recién ahí empieza: nunca se cortan entre sí.
4. Tocá **Agregar publicidad**.

**En la lista:**
- Las publicidades aparecen **ordenadas por hora** (la más temprana arriba).
- Si alguna publicidad cargada antes quedó con una hora repetida, aparece en rojo **"Hora repetida"**: tocá **Editar horas** y elegí otra.
- **Las publicidades no se cortan entre sí:** si toca una mientras otra se está viendo, espera a que termine y después empieza.
- Cada video se reproduce **una vez por día en cada hora** indicada, a pantalla completa, y después el TV vuelve a la pantalla de llamados.
- **Si llega un llamado** durante un video: el video sigue pero **en silencio**, aparece el aviso grande con el nombre y el consultorio, y al terminar el anuncio vuelve el sonido.
- El interruptor pausa una publicidad sin borrarla. **Editar horas** cambia solo las horas del turno que estás viendo (las del otro turno se mantienen).
- **Ver ahora** la reproduce en el momento; si ya hay otra en pantalla, queda en fila y empieza cuando esa termina (la extensión lo avisa). **Detener** es lo único que corta lo que se esté viendo, y vacía la fila. **Abrir en YouTube** y **Copiar link** sirven para revisar o compartir el video.
- **Copiar al otro turno:** el botón **Copiar todas a la tarde** (o **a la mañana**) de arriba pasa las publicidades del turno al otro, sumando o restando 7 horas (08:00 de la mañana → 15:00 de la tarde). Si marcás casillas, copia solo las marcadas; cada fila también tiene su botón **Copiar a la tarde / a la mañana**. Antes de copiar se abre una ventana que muestra cómo quedan las horas; si una hora ya está ocupada, se corre 4 minutos. Es la misma publicidad (el video no se duplica ni se vuelve a subir) y las horas originales no cambian. Si un turno está vacío, aparece el botón para copiar las del otro.
- **Reproducir varias:** marcá las casillas (o la de arriba para todo el turno) y tocá **Reproducir seleccionadas**: se ven una detrás de la otra, sin cortarse.
- La columna **Estado** muestra si se reprodujo bien o el motivo si falló.
- **Volumen**: llamados 70 % y publicidad 30 % por defecto (porcentaje del volumen del TV).
- Si el TV estaba apagado a esa hora, se reproduce igual si se enciende dentro de los 15 minutos.

**Recomendación:** para publicidad propia del centro, subí el video al TV. Funciona sin internet y no depende de YouTube.

## 5. PCs con otro internet u otra red

Las PCs que no están en la misma red que el TV se conectan por internet con un **código de vinculación**:

1. En el TV, apretá **OK** en el control remoto: aparece el código (16 letras y números, por ejemplo `NSCE-TKJZ-85A2-LY7H`). Abajo dice si la conexión por internet está activa.
2. En la PC, en la extensión, pestaña **Este consultorio**, sección **Conexión con el TV**, escribí el código en **Código de vinculación**, tocá **Guardar cambios** y después **Probar conexión**. Arriba a la derecha tiene que decir **TV conectado por internet**.
   - Si la PC está en la misma red que el TV, en vez de copiarlo podés tocar **Traer código del TV**.
3. Listo: al tocar el parlante, la extensión prueba primero la red local y, si no encuentra el TV, envía el llamado por internet. La primera vez tarda unos segundos más.

Cómo funciona y qué tener en cuenta:
- El TV y las PCs se encuentran en **servidores públicos de mensajería** (MQTT), sin cuentas. Todo viaja **cifrado de punta a punta** con una clave que sale del código: el servidor no puede leer los nombres de los pacientes ni mandar nada al TV.
- **El código es como una contraseña.** No lo compartas fuera del centro.
- Hace falta **internet en el TV y en la PC**. Si se corta, en la red local sigue funcionando igual.
- Por internet se puede llamar, probar y manejar la publicidad (links de YouTube, detener, seleccionar, horas, volumen). **Subir videos** solo desde la red local del TV.
- Los servidores públicos no garantizan disponibilidad. Si el centro quiere un servicio propio y estable (por ejemplo una cuenta gratuita de HiveMQ Cloud), se carga en **Servidor propio (opcional)** y se toca **Enviar al TV** desde una PC en la red del TV.

## 6. Actualizaciones automáticas

Desde la versión **2.6** la app del TV se actualiza sola. Cada 6 horas mira si hay una versión más nueva; si la hay, la descarga, comprueba que sea auténtica y la instala **de noche** (entre las 21:00 y las 06:00), cuando no hay llamados ni publicidad en pantalla. Todo se ve y se maneja desde la pestaña **Actualizaciones** de la extensión.

> **Importante:** el TV que hoy tiene la 2.5 no sabe actualizarse. La **2.6 se instala una sola vez a mano** (como en el paso 1) y desde ahí las siguientes llegan solas. Para **configurar** la dirección de actualización **por internet** (con el código de vinculación) el TV tiene que tener ya la **2.8 o más nueva**: si el TV tiene una versión anterior, instalá el APK nuevo a mano **una vez** (pendrive) y desde entonces todo se maneja desde cualquier PC. Las **fotos de los profesionales** necesitan la **2.9**.

### Qué hace falta (una sola vez)

El TV necesita un lugar de internet donde mirar. Lo más simple y gratis es **GitHub**:

1. Creá una cuenta en github.com y un repositorio **público** (por ejemplo `llamador-aguas-blancas`). No subas ahí la carpeta `firma` ni el código fuente completo: solo van los archivos de cada versión.
2. En el repositorio, **Releases › Create a new release**. Poné como título la versión (por ejemplo `2.6`) y adjuntá estos archivos:
   - `LlamadorTV-AguasBlancas.apk`
   - `actualizacion.json` (viene en la carpeta con el APK; lo genera el script `tv-app/publicar.py`)
   - `Extension-Llamador-AguasBlancas.zip` (opcional: sirve para avisar a las PCs que hay extensión nueva)
3. En una PC de la red del TV abrí la extensión › pestaña **Actualizaciones** › **De dónde se descarga** y pegá:
   `https://github.com/USUARIO/REPOSITORIO/releases/latest/download/actualizacion.json`
   (cambiando USUARIO y REPOSITORIO). Dejá marcadas las dos opciones y tocá **Guardar** y después **Buscar ahora** para probar: debe decir «Al día».

También sirve **subir los archivos a la raíz del repositorio** (sin Releases), con los mismos nombres. Entonces la dirección es `https://raw.githubusercontent.com/USUARIO/REPOSITORIO/main/actualizacion.json`. Cualquier otro lugar con una dirección `https://` también sirve (una web del centro, por ejemplo), siempre que los tres archivos estén en la misma carpeta.

**Desde qué PC se maneja:** guardar la dirección, **Buscar ahora**, **Instalar ahora** y ver el estado funcionan **desde cualquier PC, también por internet** (con el código de vinculación, sección 5). Lo único que pide estar en la **red local del TV** es **Subir desde esta PC** (mandar un APK de a pedazos).

### Cómo se publica una versión nueva

1. Compilar la app nueva y copiarla a `dist/` con el nombre `LlamadorTV-AguasBlancas.apk` (cada versión tiene que subir el número `versionCode` en `AndroidManifest.xml` y en `build.sh`).
2. Desde la carpeta `llamador/`: `python3 tv-app/publicar.py --notas "Qué cambió"` → genera `dist/actualizacion.json` con la versión y el código de verificación (SHA-256).
3. Crear una **Release nueva** en GitHub y subir el APK y `actualizacion.json` (y el .zip de la extensión si cambió). En unas horas el TV la baja y esa noche se instala. Para no esperar: pestaña **Actualizaciones › Buscar ahora** y **Instalar ahora**.

### Qué verifica el TV antes de instalar

- Que el archivo coincida con el código **SHA-256** de `actualizacion.json` (no llegó dañado ni cambiado).
- Que sea la **misma aplicación** y esté **firmada con la misma clave** (Android además lo exige al instalar). Una versión firmada con otra clave se rechaza.
- Que la versión sea **más nueva** que la instalada.

### Lo que hay que saber

- **La primera vez Android puede pedir confirmación** en el TV: aparece una pantalla de Android con **Instalar** (y quizás antes «Permitir instalar apps desconocidas de esta app»). Se acepta con el control remoto. Si nadie la acepta, la instalación se da por no hecha y se reintenta de noche (hasta 3 veces); la versión queda descargada.
- En **Android 12 o más nuevo**, después de la primera actualización hecha por la propia app, las siguientes suelen instalarse **sin preguntar**.
- Al instalar, la pantalla de llamados se cierra y se vuelve a abrir sola en uno o dos minutos. Si algún modelo de TV no la reabre, hay que abrirla con el control remoto; por eso conviene dejar la instalación automática para la noche (es lo que hace por defecto).
- Si no se quiere nada automático: desmarcá **Instalarlas solas de noche** (la versión se descarga y se instala cuando se toca **Instalar ahora**) o **Buscar y descargar automáticamente**.
- **Sin internet en el TV:** pestaña **Actualizaciones › Subir desde esta PC**: se elige el APK y se manda por la red local; el TV lo verifica igual.
- **La extensión de Chrome no se actualiza sola** (se carga desde una carpeta). Cuando el archivo de actualización trae una versión nueva de la extensión, la pestaña **Actualizaciones** y el ícono de la extensión lo avisan; para actualizarla: descargar el .zip, descomprimirlo **en la misma carpeta** de la extensión (reemplazando) y en `chrome://extensions` tocar el botón de recargar (↻).
- Si algo falla, el motivo se ve en la pestaña **Actualizaciones** (por ejemplo «el código de verificación no coincide», «firmado con otra clave» o «no se pudo conectar»).

## Preguntas frecuentes

- **El TV dice "App no instalada" o no deja instalar el APK.**
  1. Revisá que esté permitido instalar desde el administrador de archivos que usás (**Ajustes › Seguridad › Fuentes desconocidas** o, en Android 8 o más nuevo, **Ajustes › Apps › Acceso especial › Instalar apps desconocidas** › el administrador de archivos › Permitir).
  2. Si dice **"Problema al analizar el paquete"**, el archivo se copió incompleto: volvé a copiarlo al pendrive (esperá a que termine y usá "Expulsar" antes de sacarlo).
  3. Si dice **"App no instalada"** y ya había una versión del llamador de otro origen, desinstalala primero (Ajustes › Apps › Llamador Aguas Blancas › Desinstalar) y volvé a instalar. Las versiones que te pasé se instalan encima sin desinstalar.
  4. Si sigue sin instalar, sacale una foto al mensaje del TV y a **Ajustes › Información › Versión de Android**, y mandámela.

- **¿De dónde salen las voces?** La app las descarga una sola vez de las publicaciones oficiales del motor de voz libre sherpa-onnx (en GitHub) y después funcionan sin internet. No usan las voces de España ni de Estados Unidos del TV. Daniela, Claudia y Alejandro tienen acento nativo de Argentina y México; las de "latino neutro" son de un modelo multilingüe y la app adapta el texto para que digan la "c" y la "z" como "s". Si por algún motivo la voz incluida falla, el TV usa su voz del sistema para no dejar al paciente sin anunciar.
- **¿Cuánto tarda en hablar?** El nombre aparece en pantalla al instante. La voz se prepara cuando el médico apoya el mouse en el parlante y, si no, mientras suena el timbre; con Alejandro o Claudia el nombre sale apenas termina el timbre. Con las otras voces, en TVs lentos puede tardar uno o dos segundos más (la app se adapta sola a la velocidad del TV). Solo el primer llamado después de prender el TV tarda un poco más, mientras carga la voz. En la extensión, debajo de cada voz, aparece cuánto tarda en ese TV una vez que se usó.

- **¿Funciona en Odontología?** Sí: en la Estación de Trabajo de Odontología el parlante funciona igual. Se configura igual que cualquier consultorio (por ejemplo, el número del consultorio odontológico).
- **¿Funciona en otros ámbitos?** Por defecto solo envía los llamados de **Consultorio**. Se puede desmarcar en la configuración.
- **¿Qué pasa si llaman a dos pacientes casi juntos?** Se anuncian en orden, uno detrás del otro.
- **¿Y si el sistema cambia?** La extensión depende de cómo está armada la pantalla del panel (el botón `vLLAMADAS`). Si el proveedor la modifica, puede dejar de detectar el clic y hay que ajustarla.
- **Al encender el TV** la app intenta abrirse sola; algunos modelos lo bloquean, en ese caso abrila desde el inicio.

## Para generar versiones nuevas más adelante

La carpeta `fuente/tv-app/firma/` tiene la clave con la que se firmó el APK. **Guardala en un lugar seguro, con copia, y no la publiques nunca** (ni en GitHub ni en ningún lado): para instalar una versión nueva encima de la anterior —a mano o con la actualización automática— hay que firmarla con la misma clave. Si se pierde, habría que desinstalar la app de todos los TV e instalar una nueva desde cero.
