# 🔐 SECURITY+ 701 — (RIFT EDITION)

> Estructura: **Siglas (palabras completas)** → Descripción exacta y sencilla → 🎮 Ejemplo de videojuegos → 💻 Ejemplo de ciberseguridad / IT real

---

## 📊 CIA TRIAD — LAS TRES ESTADÍSTICAS BASE

**Confidentiality** (Confidencialidad)
Solo quien debe ver la información, la ve. Nadie más.
> 🎮 La niebla de guerra en League of Legends — el equipo enemigo no puede ver lo que pasa en tu lado del mapa.
> 💻 El cifrado AES-256 en un disco duro — aunque alguien robe el disco físicamente, no puede leer los datos sin la clave.

**Integrity** (Integridad)
Los datos no han sido modificados por nadie no autorizado. Lo que ves es lo real.
> 🎮 El código del juego no puede ser alterado por jugadores externos — si alguien hackea tus stats (daño, armadura), se rompe la integridad.
> 💻 Un hash SHA-256 en una transferencia de archivos — si el hash del archivo recibido no coincide con el original, sabes que fue alterado en tránsito.

**Availability** (Disponibilidad)
El sistema está accesible cuando se necesita, sin interrupciones.
> 🎮 El servidor de Riot siempre online — si cae, nadie puede jugar.
> 💻 Un clúster de servidores con failover automático — si un nodo cae, el tráfico se redirige al siguiente sin que el usuario lo note.

---

## ⚔️ DAD TRIAD — LOS ATAQUES A LA CIA

**Disclosure** (Revelación)
Información confidencial expuesta a quien no debería verla.
> 🎮 Evelynn invisible recorriendo tu jungla y viendo todos tus movimientos sin que lo notes.
> 💻 Un atacante que intercepta tráfico HTTP sin cifrar con Wireshark y lee credenciales en texto plano.

**Alteration** (Alteración)
Datos modificados sin autorización, corrompiendo su integridad.
> 🎮 Un hacker que modifica el código del servidor para cambiar tu KDA o el daño de los campeones en tiempo real — los datos ya no reflejan la realidad.
> 💻 Un ataque Man-in-the-Middle que intercepta y modifica una transferencia bancaria, cambiando el número de cuenta destino antes de que llegue al servidor.

**Denial** (Denegación)
El servicio es bloqueado y nadie puede usarlo.
> 🎮 Un ataque DDoS al servidor de Riot — miles de conexiones falsas saturan el sistema hasta que nadie puede entrar a ninguna partida.
> 💻 Un ataque DDoS volumétrico que inunda con tráfico basura el ancho de banda de un servidor web hasta dejarlo inaccesible para usuarios legítimos.

---

## 🧊 TIPOS DE CONTROL — LAS DEFENSAS

**Preventive** (Preventivo)
Evita que el ataque ocurra antes de que pase.
> 🎮 Poner wards antes del gank — prevención antes de que el enemigo entre.
> 💻 Un firewall con reglas que bloquean puertos no autorizados antes de que cualquier tráfico malicioso llegue a la red interna.

**Detective** (Detectivo)
Identifica que algo malo está ocurriendo o ya ocurrió.
> 🎮 Ver al jungler enemigo aparecer en el minimapa — lo detectas cuando ya está actuando.
> 💻 Un SIEM (Security Information and Event Management — sistema que centraliza logs y genera alertas de seguridad) que analiza logs y dispara una alerta cuando detecta múltiples intentos fallidos de login en menos de 60 segundos.

**Corrective** (Correctivo)
Minimiza el daño y restaura el sistema después de que el incidente ocurrió.
> 🎮 Activar Guardian Angel (GA) al morir y seguir peleando — corriges la situación tras el golpe.
> 💻 Restaurar un servidor desde un backup limpio después de un ataque de ransomware — el sistema vuelve a operar desde el último punto seguro conocido.

**Deterrent** (Disuasivo)
Desanima al atacante antes de que actúe, sin bloquearlo directamente.
> 🎮 En el equipo enemigo hay campeón tanque con 5,000 HP visible en el mapa, tu jhin aliado tiene armado coleccionista. Lo evalúas y decides no hacer engage porque sabes que esa TF es perder el tiempo.
> 💻 Un cartel de "sistema monitorizado 24/7 — toda actividad queda registrada" en la pantalla de login — reduce intentos de acceso no autorizado sin bloquear nada técnicamente.

**Compensating** (Compensatorio)
Alternativa que reemplaza al control principal cuando este no está disponible.
> 🎮 Si tu main está baneado, juegas tu secundario — cumples el mismo objetivo con otro recurso.
> 💻 Si no se puede implementar MFA en un sistema legacy, se añade monitorización intensiva de sesiones y restricción por IP como control alternativo.

**Directive** (Directivo)
Políticas o reglas que indican cómo debe actuar la gente.
> 🎮 Las reglas del chat de Riot — dictan el comportamiento esperado.
> 💻 La política de contraseñas de la empresa que obliga a usar mínimo 12 caracteres, mayúsculas, números y símbolos — no bloquea nada técnicamente, pero define el estándar obligatorio.

---

## 🏷️ CATEGORÍAS DE CONTROL

**Technical** (Técnico)
Implementado por software o hardware directamente.
> 🎮 Vanguard, el anti-cheat de Riot que detecta trampas automáticamente.
> 💻 Un IPS que bloquea automáticamente una IP que genera tráfico malicioso, sin intervención humana.

**Managerial** (Gerencial)
Políticas, estrategia y administración del riesgo a nivel directivo.
> 🎮 El coach definiendo la estrategia de draft y composición antes de la partida.
> 💻 Un risk assessment trimestral donde el CISO evalúa amenazas, prioriza inversiones en seguridad y aprueba el presupuesto de controles.

**Operational** (Operacional)
Ejecutado por personas en el día a día, no por software.
> 🎮 El shotcaller tomando decisiones en tiempo real durante el teamfight.
> 💻 El equipo de SOC (Security Operations Center — centro de operaciones de seguridad que monitorea y responde a incidentes) revisando alertas del SIEM cada turno, investigando anomalías y escalando incidentes manualmente.

**Physical** (Físico)
Barreras o controles tangibles en el mundo real.
> 🎮 El net café con puertas cerradas y guardia en la entrada — solo entran los que tienen autorización física.
> 💻 Un data center con lector de tarjeta RFID, cámara en la puerta y jaula de servidores con cerradura — el acceso físico al hardware está controlado independientemente del acceso lógico.

---

## 🦸 THREAT ACTORS — TIPOS DE ENEMIGOS

**Script Kiddie**
Atacante sin habilidades propias que usa herramientas ya creadas por otros.
> 🎮 Teemo — molesto, sin mecánicas avanzadas, usa shrooms prefabricados que cualquiera podría activar.
> 💻 Alguien que descarga Metasploit o un exploit kit de GitHub sin entender cómo funciona y lo lanza contra servidores aleatorios buscando vulnerabilidades conocidas.

**Hacktivist** (Hacktivista)
Atacante motivado por una causa política o social, no por dinero.
> 🎮 Vi — su lore entero gira en torno a luchar por justicia en los Undercity. No ataca por dinero, ataca porque cree que es lo correcto.
> 💻 Anonymous desfigurando la web de un gobierno para protestar contra una ley — el objetivo es visibilidad y presión política, no beneficio económico.

**Organized Crime** (Crimen organizado)
Grupo estructurado con recursos y motivación puramente financiera.
> 🎮 Gangplank — sindicato pirata con organización, motivado únicamente por el oro.
> 💻 Un grupo criminal que opera ransomware-as-a-service con desarrolladores, negociadores, operadores de C2 y lavado de criptomonedas. Estructura empresarial criminal completa.

**Nation-State / APT** (Estado-nación / Amenaza persistente avanzada)
Actor patrocinado por un gobierno, con recursos ilimitados y ataques sostenidos a largo plazo.
> 🎮 Aurelion Sol — aparece poco, pero cuando lo hace borra el mapa por completo.
> 💻 El grupo Lazarus (Corea del Norte) infiltrando redes de bancos internacionales durante meses sin ser detectado, exfiltrando millones antes de activar el payload final.

**Insider Threat** (Amenaza interna)
La amenaza viene de alguien que ya tiene acceso legítimo dentro de la organización.
> 🎮 Singed — juega en tu equipo pero te tira veneno. Es tu aliado y te daña.
> 💻 Un sysadmin con acceso privilegiado que copia la base de datos de clientes a un USB antes de renunciar, o que sabotea sistemas por resentimiento.

**Competitor** (Competidor)
Actor que busca ventaja competitiva espiando o robando información.
> 🎮 Twitch invisible siguiéndote por el mapa para ver tu build y reportarla al equipo enemigo sin que lo notes.
> 💻 Una empresa que contrata a un ex-empleado de la competencia para obtener acceso a roadmaps, precios o código fuente propietario — espionaje corporativo.

---

## 🦠 MALWARE — TIPOS DE PLAGAS

**Virus**
Se adjunta a archivos existentes y necesita que el usuario lo ejecute para propagarse.
> 🎮 Un mod de skin que lleva código malicioso oculto — el usuario lo instala creyendo que es legítimo, y el virus se activa al abrir el juego.
> 💻 Un archivo .exe adjunto en un correo de phishing — al hacer doble clic, inyecta código en procesos legítimos del sistema como explorer.exe.

**Worm** (Gusano)
Se auto-replica por la red sin necesitar ninguna acción del usuario. Consume ancho de banda.
> 🎮 Karthus — su ulti golpea a todos los enemigos del mapa automáticamente sin interactuar con ninguno.
> 💻 WannaCry propagándose por SMB (puerto 445) — sin que nadie haga clic en nada, salta de máquina en máquina explotando EternalBlue hasta infectar miles de equipos en horas.

**Trojan** (Troyano)
Parece un programa legítimo pero lleva código malicioso oculto adentro.
> 🎮 Neeko — se disfraza de tu ADC aliado y parece confiable hasta que actúa.
> 💻 Un "generador de claves" de software pirata que instala un RAT (Remote Access Trojan) en segundo plano mientras muestra una clave falsa al usuario.

**Ransomware**
Cifra tus archivos y exige un pago para devolverte el acceso.
> 🎮 Mordekaiser — te secuestra en el Reino de los Muertos. No puedes hacer nada hasta que termine.
> 💻 LockBit cifrando todos los archivos de un hospital y mostrando una nota de rescate — los médicos no pueden acceder a historiales clínicos hasta que se pague en cripto.

**Rootkit**
Se esconde en el kernel del sistema operativo, invisible para el antivirus y el OS.
> 🎮 Evelynn — invisible en el mapa, ni el equipo enemigo la detecta con el radar normal.
> 💻 Un rootkit que modifica las llamadas al sistema operativo para ocultarse — cuando el antivirus lista procesos o archivos, el rootkit filtra su propia entrada de los resultados.

**Spyware**
Roba información sigilosamente sin que el usuario lo note.
> 🎮 Twitch — te observa desde la invisibilidad y recopila información antes de atacar. A diferencia de Evelynn (Rootkit), que se esconde en el sistema mismo, Twitch extrae datos activamente.
> 💻 Un stalkerware en un teléfono que envía GPS, mensajes y capturas de pantalla a un servidor remoto sin ninguna notificación visible para el dueño del dispositivo.

**Adware**
Muestra publicidad no deseada de forma constante. A veces deriva en spyware.
> 🎮 Un launcher de juego gratuito que muestra anuncios cada vez que lo abres y cada vez que terminas una partida — molesto, inevitable, y a veces recopila tus datos en segundo plano.
> 💻 Una extensión de navegador gratuita que inyecta banners en cada página que visitas y redirige tus búsquedas a través de sus propios servidores para perfilarte y vender esos datos.

**Keylogger**
Captura cada tecla que el usuario presiona y la envía al atacante.
> 🎮 Un mod de chat que registra silenciosamente todo lo que escribes — usuario, contraseña, mensajes — y lo envía a un servidor externo sin que lo notes.
> 💻 Un keylogger de hardware conectado entre el teclado y el PC en un puesto de trabajo — captura credenciales físicamente sin dejar rastro en el sistema operativo.

**Fileless Malware** (Malware sin archivos)
Vive únicamente en la RAM. No escribe nada en disco, muy difícil de detectar.
> 🎮 Nocturne — opera en tus pesadillas (RAM), no deja rastro en disco al despertar.
> 💻 Un payload ejecutado directamente en PowerShell en memoria — no toca el disco, no activa antivirus basados en firmas de archivos, y desaparece al reiniciar el sistema.

**Logic Bomb** (Bomba lógica)
Código dormido que se activa solo cuando se cumple una condición específica.
> 🎮 La pasiva de Karthus — el código explota cuando muere (trigger condicional).
> 💻 Un ex-empleado que deja código en el sistema de nóminas que borra registros si su nombre desaparece de la base de datos de empleados activos.

**Botnet**
Red de computadoras infectadas controladas remotamente por un servidor central (C2 — Command and Control, servidor que gestiona dispositivos infectados remotamente).
> 🎮 Malzahar con su enjambre de voidlings — él es el C2, los voidlings son los zombies que obedecen sus órdenes.
> 💻 Mirai infectando routers y cámaras IP vulnerables para construir una red de cientos de miles de dispositivos que luego lanzó el DDoS más grande de 2016 contra Dyn.

---

## 🗝️ CRIPTOGRAFÍA

**Symmetric Encryption / AES** (Cifrado simétrico / Advanced Encryption Standard)
Una sola llave cifra y descifra. Rápido. El mismo secreto lo tienen ambas partes.
> 🎮 Un código secreto que solo conoce tu equipo — todos lo usan para comunicarse en un canal privado. Si alguien externo intercepta el mensaje sin la clave, no entiende nada.
> 💻 AES-256 cifrando el disco de un laptop con BitLocker — una sola clave derivada de tu contraseña cifra y descifra todo el volumen. Sin ella, los datos son ruido aleatorio.

**Asymmetric Encryption / RSA (Rivest-Shamir-Adleman: Algoritmo de Cifrado Asimetrico, uno de los mas importantes) / ECC(Elliptic-Curve Cryptography)** (Cifrado asimétrico)
Par de llaves: una pública (todos la tienen) y una privada (solo el dueño). Más lento.
> 🎮 Braum — su escudo público protege a todos, pero solo él puede activar o bajar el escudo privado.
> 💻 SSH con par de claves — el servidor tiene tu clave pública, tú guardas la privada. El servidor cifra un reto con tu pública, solo tu privada puede descifrarlo y autenticarte sin contraseña.

**Hashing / SHA-256(Hash Algorimth)** (Secure Hash Algorithm)
Convierte cualquier dato en un valor fijo e irreversible (one-way). No se puede deshacer.
> 🎮 Akali entrando a su humo — no puedes rastrear de dónde vino ni volver al punto de entrada. Proceso sin retorno.
> 💻 Las contraseñas en una base de datos se guardan como hashes SHA-256, no en texto plano. Si alguien roba la BD, no puede recuperar la contraseña original, solo comparar hashes.

**Digital Signature** (Firma digital)
Firmás con tu llave privada. Cualquiera con tu llave pública puede verificar que fuiste tú. Garantiza no repudio.
> 🎮 Tu contrato firmado en Master+ — Riot registra que tú jugaste esa partida. No puedes decir "yo no fui".
> 💻 Un correo firmado digitalmente con S/MIME — el receptor verifica con tu clave pública que el mensaje vino de ti y no fue modificado en tránsito. No puedes negarlo.

**PKI** (Public Key Infrastructure — Infraestructura de llave pública)
Sistema de autoridades (CA — Certificate Authority, entidad que emite certificados; RA — Registration Authority, entidad que verifica identidad antes de solicitar un certificado) que emiten y gestionan certificados digitales de identidad.
> 🎮 La Comisión de Runaterra — solo ellos emiten pergaminos de identidad verificados. Si no viene sellado por ellos, no vale.
> 💻 DigiCert o Let's Encrypt actuando como CA — emiten certificados TLS que los navegadores confían. Sin ese sello, el navegador muestra "Conexión no segura".

**TLS / HTTPS** (Transport Layer Security / HyperText Transfer Protocol Secure)
Canal cifrado entre cliente y servidor. Combina cifrado asimétrico (handshake) y simétrico (datos).
> 🎮 El chat privado de equipo durante la partida — solo tu equipo lee los mensajes, nadie de afuera puede interceptarlos.
> 💻 Tu banco en HTTPS — el handshake TLS negocia las claves con RSA/ECC, y luego toda la sesión viaja cifrada con AES. Wireshark solo ve ruido cifrado.

**Perfect Forward Secrecy** (Secreto perfecto hacia adelante)
Genera una llave nueva por sesión. Si comprometen una sesión pasada, las demás siguen seguras.
> 🎮 Cada custom game tiene una contraseña temporal distinta y descartable — si alguien roba la contraseña de la partida de ayer, no puede entrar a la de hoy.
> 💻 TLS con ECDHE(Protocolo de encriptacion) — cada sesión genera un par de claves efímeras. Si un atacante graba tráfico cifrado hoy y consigue tu clave privada en el futuro, no puede descifrar sesiones pasadas.

---

## 🌐 REDES — EL MAPA

**DMZ** (Demilitarized Zone — Zona desmilitarizada)
Subred pública separada de la red interna. Aloja servidores accesibles desde internet.
> 🎮 La calle (lane) — zona pública donde todos pelean, aislada de tu base.
> 💻 El servidor web de una empresa en la DMZ — accesible desde internet, pero si es comprometido, el firewall interno impide que el atacante salte a la red corporativa.

**Firewall**
Filtra el tráfico de red según reglas definidas. Distintos niveles de inspección según el tipo.
> 🎮 Las torretas — distintos niveles: torreta básica (filtra por IP/puerto), con memoria (stateful), con visión verdadera (NGFW).
> 💻 Un firewall perimetral con reglas ACL (Access Control List — lista de reglas ordenadas que permiten o deniegan tráfico) que bloquea todo el tráfico entrante excepto los puertos 443 (HTTPS) y 22 (SSH) hacia servidores específicos.

**Packet-Filtering Firewall** (Firewall de filtrado de paquetes)
Bloquea o permite tráfico por IP, puerto y protocolo. No recuerda conexiones anteriores.
> 🎮 Torreta Tier 1 — bloquea lo que pasa por delante, pero no recuerda si ese minion ya había pasado antes.
> 💻 Una ACL en un router Cisco que permite solo los puertos 80 y 443 desde cualquier IP — evalúa cada paquete individualmente, sin contexto de si forma parte de una sesión legítima.

**Stateful Inspection Firewall** (Firewall de inspección de estado)
Recuerda el estado de las conexiones activas para decisiones más inteligentes.
> 🎮 Torreta Tier 2 — recuerda que ese minion ya pasó antes y ajusta su respuesta.
> 💻 Un firewall stateful que permite respuestas a conexiones iniciadas desde adentro — si el cliente interno inició la sesión TCP, deja pasar la respuesta. Si llega un paquete sin handshake previo, lo bloquea.

**NGFW** (Next-Generation Firewall — Firewall de próxima generación)
Deep packet inspection + IDS/IPS (Intrusion Detection System / Intrusion Prevention System — sistema que detecta y/o bloquea tráfico malicioso) + anti-malware, todo integrado en un solo dispositivo.
> 🎮 Torreta + inhibidor + visión verdadera — ve todo, analiza todo y bloquea amenazas avanzadas.
> 💻 Palo Alto NGFW inspeccionando tráfico HTTPS cifrado, identificando la aplicación (no solo el puerto), detectando firmas de malware en el payload y bloqueando en tiempo real.

**IDS** (Intrusion Detection System — Sistema de detección de intrusiones)
Monitorea y alerta sobre actividad sospechosa. Solo detecta, no bloquea.
> 🎮 Lee Sin Q — revela al enemigo en el mapa pero no lo detiene, solo lo expone.
> 💻 Snort en modo IDS — analiza el tráfico de red y genera alertas en el SIEM cuando detecta patrones de escaneo de puertos o firmas de exploit, pero no corta ninguna conexión.

**IPS** (Intrusion Prevention System — Sistema de prevención de intrusiones)
Detecta y bloquea activamente el tráfico malicioso en tiempo real.
> 🎮 la R de Ashe — Revela  todo lo que entra a su rango de vision mientras viaja a su destino. Tambien lo detiene cuand coliciona con este.

> 💻 Snort en modo IPS inline — está en el path del tráfico. Cuando detecta un exploit conocido, descarta el paquete antes de que llegue al servidor destino.

**VPN** (Virtual Private Network — Red privada virtual)
Crea un túnel cifrado para comunicación segura a través de redes públicas.
> 🎮 Evelynn moviéndose por el mapa — nadie sabe por dónde va ni puede rastrearla. Llega a su destino de forma completamente oculta.
> 💻 Un empleado remoto conectándose por OpenVPN — todo su tráfico viaja cifrado hasta el gateway corporativo. Para el ISP solo es ruido cifrado hacia una IP.

**NAC** (Network Access Control — Control de acceso a la red)
Verifica que un dispositivo cumple requisitos de seguridad antes de dejarlo entrar a la red.
> 🎮 El anti-cheat al iniciar partida — si no cumples los requisitos, el sistema no te deja entrar.
> 💻 Cisco ISE verificando antes de dar acceso a la LAN corporativa — si el equipo no tiene antivirus actualizado, parches al día y certificado de dominio, lo manda a una VLAN (Virtual Local Area Network — segmentación lógica de redes) de cuarentena.

**SIEM** (Security Information and Event Management — Gestión de información y eventos de seguridad)
Centraliza logs de toda la red, detecta patrones y genera alertas de seguridad.
> 🎮 Caitlyn con trampas por todo el mapa + ulti que revela a todos los enemigos — cobertura total y visión global.
> 💻 Splunk correlacionando logs de firewall, AD, endpoints y proxies — detecta que el mismo usuario falló login 50 veces en 2 minutos desde una IP en Rusia y dispara una alerta crítica.

**SOAR** (Security Orchestration, Automation and Response — Orquestación, automatización y respuesta de seguridad)
Automatiza la respuesta a incidentes de seguridad sin intervención manual.
> 🎮 Vi con su combo Q→AA→E→R — automatización de respuesta que una vez iniciada no puedes parar.
> 💻 Palo Alto XSOAR recibiendo una alerta de phishing — automáticamente bloquea el dominio en el proxy, aísla el endpoint, abre un ticket en Jira y notifica al analista, todo en segundos.

**Load Balancer** (Balanceador de carga)
Distribuye el tráfico entre varios servidores para evitar que uno se sature.
> 🎮 El matchmaking — distribuye jugadores entre servidores según carga para que ninguno explote.
> 💻 Un F5 BIG-IP distribuyendo peticiones HTTP entre 10 servidores web — si uno llega al 90% de CPU o falla, el balanceador deja de enviarle tráfico automáticamente.

**Proxy**
Actúa como intermediario entre un cliente y un servidor externo.
> 🎮 El proxy farming de Singed — se posiciona entre el enemigo y su torreta, absorbiendo la atención y canalizando el tráfico.
> 💻 Un proxy corporativo (Zscaler) por el que sale todo el tráfico web de los empleados — inspecciona URLs, aplica filtros de contenido y registra cada petición antes de reenviarla a internet.

**ACL** (Access Control List — Lista de control de acceso)
Lista de reglas ordenadas que permiten o deniegan tráfico. Se procesan de arriba hacia abajo.
> 🎮 El sistema de mute de Riot — permiso o denegado según reglas aplicadas en orden.
> 💻 Una ACL en un switch que permite tráfico del VLAN 10 al servidor de archivos en el puerto 445, deniega todo lo demás, y procesa las reglas de arriba a abajo hasta encontrar un match.

**DNS** (Domain Name System)
---
Funciona como la agenda telefonica de Internet. Su funcion principal es traducir los nombres de las paginas web que escribimos (google.com[ <-- Un dominio]) en direcciones IP numericas como (142.250.190.46) que son las computadoras
## 🔐 IAM — ROLES Y PERMISOS

**Dominio**
la URL de una pagina web es lo que consideramos un dominio, es una direccion facil de recordar que representa la direccion IP del sitio.

**Identification** (Identificación)
Declarar quién eres ante el sistema. Sin probar nada todavía.
> 🎮 Pickear campeón — declaras quién eres en esta partida.
> 💻 Escribir tu nombre de usuario en el campo de login — el sistema sabe a quién buscar, pero todavía no ha verificado nada.

**Authentication** (Autenticación)
Probar que eres quien dices ser.
> 🎮 Loguearte al cliente de Riot — demuestras que eres el dueño real de esa cuenta.
> 💻 Introducir tu contraseña o pasar un desafío de MFA — el sistema valida que tienes el secreto que solo el dueño legítimo debería tener.

**Authorization** (Autorización)
Qué tienes permiso de hacer una vez que tu identidad fue verificada.
> 🎮 El rol asignado en champ select — mid no toca la jungla, cada rol tiene sus límites.
> 💻 Un developer autenticado que puede leer el repositorio de código pero no puede hacer push a main — sus credenciales son válidas, pero sus permisos están limitados por rol.

**Accounting / Audit** (Contabilidad / Auditoría)
Registro de todo lo que hiciste en el sistema. Trazabilidad total.
> 🎮 El post-game lobby — KDA, daño, wards, todo queda registrado y no se puede borrar.
> 💻 Los logs de Active Directory registrando cada inicio de sesión, cada cambio de permiso y cada acceso a un recurso — si hay un incidente, el forense reconstruye exactamente qué pasó y cuándo.

**MFA** (Multi-Factor Authentication — Autenticación multifactor)
Verificación con dos o más factores de categorías distintas. No basta con dos contraseñas.
> 🎮 Cliente de Riot + SMS + huella = tres factores de categorías distintas para entrar.
> 💻 Login con contraseña (algo que sabes) + código TOTP de Google Authenticator (algo que tienes) — si roban la contraseña, sin el teléfono no pueden entrar.

**RBAC** (Role-Based Access Control — Control de acceso basado en roles)
Los permisos se asignan por rol, no por usuario individual.
> 🎮 Roles en ranked — ADC farmea, Supp protege, Jungler smitea. Cada rol tiene acciones definidas y no invade las del otro.
> 💻 En Azure AD, el rol "Reader" puede ver recursos pero no modificarlos; "Contributor" puede crear y editar; "Owner" puede gestionar permisos. El acceso se hereda del rol, no se configura por persona.

**ABAC** (Attribute-Based Access Control — Control de acceso basado en atributos)
El acceso depende de condiciones o atributos específicos del usuario, entorno o recurso.
> 🎮 Runas condicionales — si eres ADC y tienes Fleet Footwork equipado, obtienes curación extra. El sistema evalúa atributos antes de dar el beneficio.
> 💻 Una política que permite acceso a documentos clasificados solo si: el usuario es del departamento Legal, está en la red corporativa y el documento tiene clasificación ≤ Confidential. Los tres atributos deben cumplirse simultáneamente.

**MAC** (Mandatory Access Control — Control de acceso obligatorio)
El sistema impone los niveles de acceso. El usuario no puede cambiarlos aunque quiera.
> 🎮 El sistema de honor de Riot — el sistema decide si puedes chatear, no el jugador.
> 💻 SELinux en un servidor Linux — el sistema operativo impone etiquetas de seguridad a cada proceso y archivo. Ni el root puede acceder a recursos fuera de su etiqueta definida por política.

**DAC** (Discretionary Access Control — Control de acceso discrecional)
El dueño del recurso decide quién puede acceder.
> 🎮 El que hostea la custom game decide quién entra y con qué equipo.
> 💻 El propietario de una carpeta compartida en Windows que decide qué usuarios o grupos tienen lectura o escritura — el control está en manos del dueño del recurso, no del sistema central.

**SSO** (Single Sign-On — Inicio de sesión único)
Una sola autenticación da acceso a múltiples sistemas del ecosistema.
> 🎮 Login con Google para entrar al cliente de Riot — una cuenta, acceso a todos los juegos del ecosistema.
> 💻 Okta SSO en una empresa — el empleado se autentica una vez y accede sin volver a loguearse a Slack, Salesforce, GitHub y Jira, porque todos confían en el token de Okta.

**Federation** (Federación)
Dos organizaciones distintas se confían mutuamente para compartir identidad de usuarios.
> 🎮 Riot y Discord — confianza mutua entre plataformas para compartir tu identidad sin crear una cuenta nueva.
> 💻 Una empresa que usa su Azure AD federado con el AD de un partner externo — el empleado del partner se autentica con sus credenciales propias y accede a los recursos compartidos sin una cuenta adicional.

**Least Privilege** (Mínimo privilegio)
Cada usuario solo tiene los permisos mínimos necesarios para su función, nada más.
> 🎮 El supp no toma el blue buff — solo usa lo necesario para su rol.
> 💻 Una cuenta de servicio que solo tiene permisos de lectura sobre la tabla de base de datos que necesita consultar — si esa cuenta es comprometida, el atacante no puede escribir, borrar ni acceder a otras tablas.

**PAM** (Privileged Access Management — Gestión de acceso privilegiado)
Control especial sobre cuentas con permisos elevados. Incluye logs, MFA extra y tiempo limitado.
> 🎮 Permisos de capitán en Clash — tienes control especial, pero con auditoría y verificación adicional.
> 💻 CyberArk gestionando cuentas de administrador — las contraseñas root rotan automáticamente, cada sesión privilegiada queda grabada en video, y el acceso expira después de un tiempo definido.

---

## 🚑 INCIDENT RESPONSE — EL PROTOCOLO DE EMERGENCIA

**Preparation** (Preparación)
Tener todo listo antes de que ocurra el incidente: herramientas, planes, equipo entrenado.
> 🎮 Pick/Ban + Runas — tienes anti-cheat activo, plan de juego y equipo listo antes de que empiece la partida.
> 💻 Tener el playbook de IR documentado, el SIEM configurado, los backups verificados y el equipo SOC con tabletop exercises hechos — todo antes de que ocurra el primer incidente real.

**Identification** (Identificación)
Detectar que el incidente está ocurriendo usando logs, alertas e IoCs (Indicators of Compromise — evidencias como IPs, hashes o patrones que señalan una intrusión).
> 🎮 Ver al jungler enemigo aparecer en el mapa — "¡mid mia!", el ataque fue detectado.
> 💻 El SIEM dispara una alerta por tráfico de C2 beaconing hacia una IP en lista negra — el analista confirma que es un incidente real, no un falso positivo, y lo declara formalmente.

**Containment** (Contención)
Limitar el daño. Aislar el sistema comprometido sin eliminar la amenaza todavía.
> 🎮 Flash + barrera y ponerse bajo torreta — limitas el daño y te pones a salvo antes de contraatacar.
> 💻 Aislar el endpoint infectado de la red (VLAN de cuarentena o desconexión física) y revocar sus credenciales — el malware queda atrapado, sin poder comunicarse con el C2 ni moverse lateralmente.

**Eradication** (Erradicación)
Eliminar la amenaza por completo del sistema.
> 🎮 Focus y eliminar al carry enemigo — limpias la amenaza de raíz.
> 💻 Reimagear el endpoint infectado desde golden image, parchear la vulnerabilidad explotada y eliminar todas las cuentas y backdoors creados por el atacante.

**Recovery** (Recuperación)
Restaurar las operaciones normales de forma segura.
> 🎮 Respawn + TP a lane — vuelves a jugar con operaciones normales restauradas.
> 💻 Restaurar el servidor desde backup limpio, verificar integridad de datos, monitorear intensivamente durante 72 horas y declarar el sistema operativo una vez confirmado que no hay reinfección.

**Lessons Learned** (Lecciones aprendidas)
Post-mortem: qué salió mal, qué mejorar para el siguiente incidente.
> 🎮 El post-game review — analizas la partida para no repetir los mismos errores.
> 💻 Reunión post-incidente donde el equipo documenta la línea de tiempo del ataque, identifica qué control falló y actualiza el playbook y las reglas del SIEM para detectar antes el mismo vector.

---

## 🔑 CRIPTOGRAFÍA — ALGORITMOS (TABLA DE RAREZA)

| Algoritmo | Estado | Notas |
|-----------|--------|-------|
| **MD5** | ❌ Roto | Colisiones conocidas — no usar ni para checksums |
| **SHA-1** | ❌ Deprecado | Roto desde 2017, browsers ya no lo aceptan |
| **SHA-256** | ✅ Estándar actual | Gold standard para hashing |
| **HMAC** | ✅ Seguro | Hash + llave = autenticación e integridad |
| **AES-256** | ✅ Gold standard | Cifrado simétrico de referencia |
| **RSA 4096** | ✅ Seguro | Lento pero robusto para asimétrico |
| **ECC** | ✅ Seguro y eficiente | Más rápido que RSA con igual seguridad |
| **DES / 3DES** | ❌ Obsoleto | Deprecado por NIST en 2023 |

---

## 📋 GESTIÓN DE RIESGOS

**SLE** (Single Loss Expectancy — Pérdida esperada por evento único)
Cuánto pierdes económicamente si el incidente ocurre una sola vez.
> 🎮 El gold que pierdes si mueres una vez.
> 💻 Si un servidor de producción cae, SLE = coste por hora de downtime × horas promedio de recuperación + daño reputacional estimado.

**ARO** (Annual Rate of Occurrence — Tasa anual de ocurrencia)
Cuántas veces se espera que ocurra el incidente en un año.
> 🎮 Cuántas veces mueres por partida en promedio.
> 💻 Si históricamente el servidor ha caído 3 veces en 2 años, el ARO = 1.5. Se basa en datos históricos o tablas actuariales del sector.

**ALE** (Annual Loss Expectancy — Pérdida anual esperada) = SLE × ARO
El impacto económico total estimado que ese riesgo genera en un año.
> 🎮 SLE × ARO = gold perdido total en toda la temporada.
> 💻 SLE de $50,000 × ARO de 1.5 = ALE de $75,000 anuales. Si un control cuesta $20,000/año y reduce el ARO a 0.5, el ALE baja a $25,000 — el control se justifica económicamente.

**RTO** (Recovery Time Objective — Objetivo de tiempo de recuperación)
Cuánto tiempo máximo puede estar caído el sistema antes de restaurarlo.
> 🎮 Cuánto tardas en revivir y volver a lane.
> 💻 El SLA dice RTO = 4 horas — si el sistema de pagos cae, tienes 4 horas para restaurarlo antes de incumplir el acuerdo y enfrentar penalizaciones.

**RPO** (Recovery Point Objective — Objetivo de punto de recuperación)
Cuánta información puedes permitirte perder, medida en tiempo hacia atrás.
> 🎮 Cuánto exp y gold perdiste desde el último checkpoint.
> 💻 RPO = 1 hora significa backups cada hora — si el sistema falla, como máximo pierdes 60 minutos de transacciones. Si RPO = 0, necesitas replicación en tiempo real.

---

## 💾 BACKUPS — EL SISTEMA DE REPLAY

| Tipo | Velocidad backup | Velocidad restore | 🎮 Videojuegos | 💻 IT Real |
|------|-----------------|------------------|---------------|-----------|
| **Full** | Lenta | Rápida | Guardar el replay completo de la partida | Snapshot completo de la VM — restaurar es directo, pero ocupa mucho espacio y tarda en hacerse |
| **Incremental** | Rápida | Lenta | Solo los últimos 5 minutos desde el backup anterior | Solo los bloques cambiados desde el último backup — restaurar requiere encadenar todos los incrementales |
| **Differential** | Media | Media | Todo desde el último Full | Solo los cambios desde el último Full — restaurar necesita el Full + el último Differential |

**Regla 3-2-1:** 3 copias de datos, en 2 tipos de medios distintos, 1 copia fuera del sitio (offsite o cloud).

---

## 🏗️ SITIOS DE CONTINGENCIA (BC/DR)

**Hot Site** (Sitio caliente)
Réplica exacta y activa del sistema. Activación en segundos.
> 🎮 Tener un smurf en Challenger listo para jugar — sin warm-up, entra directo.
> 💻 Un datacenter secundario con servidores encendidos y datos replicados en tiempo real — si el primario cae, el secundario asume en segundos sin intervención manual.

**Warm Site** (Sitio tibio)
Infraestructura parcialmente lista. Necesita configuración antes de activarse. Horas.
> 🎮 Una cuenta en Diamante — lista pero necesita unas partidas de calentamiento antes de rendir al máximo.
> 💻 Servidores preinstalados en el site secundario pero sin datos actualizados — al activarse hay que restaurar los últimos backups y configurar las aplicaciones antes de redirigir el tráfico.

**Cold Site** (Sitio frío)
Solo el espacio físico y la infraestructura básica. Necesita instalación completa. Días.
> 🎮 Una cuenta nivel 30 sin ranked — tienes la base, pero toca grindear todo desde cero.
> 💻 Una sala de datacenter con racks vacíos y electricidad — si el primario cae, hay que instalar hardware, OS, restaurar backups y reconfigurar todo antes de poder operar.

---

## 🔍 PEN TESTING — TIPOS DE PRUEBA

**Black Box** (Caja negra)
El tester no tiene ningún conocimiento previo del sistema objetivo.
> 🎮 Jugar contra un equipo que nunca has visto — no sabes su composición ni su estilo.
> 💻 Un pentester externo que solo recibe el nombre del dominio — simula exactamente lo que haría un atacante real sin información privilegiada.

**White Box** (Caja blanca)
El tester tiene acceso completo: código fuente, arquitectura, credenciales, documentación.
> 🎮 Ver el replay completo del enemigo antes del match — conoces cada decisión que tomaron.
> 💻 Un auditor con acceso al código fuente, diagramas de red y credenciales de admin — puede revisar lógica de negocio, configuraciones internas y vulnerabilidades solo visibles desde adentro.

**Gray Box** (Caja gris)
Conocimiento parcial del sistema — entre black y white box.
> 🎮 Sabes qué campeón juega el mid pero no conoces su build ni sus runas.
> 💻 Un pentester con credenciales de usuario estándar pero sin acceso admin — simula un atacante que ya comprometió una cuenta de bajo privilegio y busca escalar.

---

## 📊 TABLA RESUMEN — CHEAT CODES

| Concepto | Fórmula / Frase clave |
|----------|----------------------|
| **CIA** | Confidentiality, Integrity, Availability |
| **DAD** | Disclosure, Alteration, Denial |
| **IR Lifecycle** | Preparation → Identification → Containment → Eradication → Recovery → Lessons Learned |
| **Mnemotecnia IR** | **P**ick **I**dentify **C**ontain **E**radicate **R**ecover **L**earn |
| **Cyber Kill Chain** | Recon → Weaponize → Deliver → Exploit → Install → C2 → Act |
| **NIST CSF** | Identify → Protect → Detect → Respond → Recover |
| **SLE / ARO / ALE** | SLE × ARO = ALE |
| **3-2-1 Backup** | 3 copias, 2 medios, 1 offsite |
| **RTO / RPO** | RTO = tiempo para restaurar \| RPO = cuánta data perder |
| **AuthN vs AuthZ** | AuthN = ¿Quién eres? \| AuthZ = ¿Qué puedes hacer? |
| **Symmetric vs Asymmetric** | Sym = 1 llave, rápido (AES) \| Asym = par de llaves, lento (RSA/ECC) |
| **Hashing** | One-way. SHA-256 = seguro. MD5/SHA-1 = rotos. |
| **IDS vs IPS** | IDS = solo detecta \| IPS = detecta + bloquea |
| **WEP → WPA2 → WPA3** | WEP = roto. WPA2 = AES mínimo. WPA3 = SAE + forward secrecy |
| **SFTP vs FTPS** | SFTP = FTP sobre SSH \| FTPS = FTP sobre TLS. NO son lo mismo. |
| **IPsec** | AH (autentica) + ESP (cifra). Tunnel = site-to-site, Transport = host-to-host |
| **CVSS** | 0 = None → 10 = Critical |
| **PKI Flow** | CA emite → RA verifica → Cert vincula identidad → CRL/OCSP chequean validez |

---

> *"GG. Ya tienes el conocimiento y los ejemplos correctos. Ahora toca aplicarlo."*
