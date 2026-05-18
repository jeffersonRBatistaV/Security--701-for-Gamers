# 🎮 SECURITY+ 701 — para Gamers

> **Estructura de cada concepto:** Sigla (palabras completas) → Descripción exacta → 🎮 Ejemplo de videojuegos → 💻 Ejemplo real en IT → 🔗 Conecta con otras secciones

---

## ⚖️ DOMINIOS DEL EXAMEN — LO QUE VALE PUNTOS

El examen SY0-701 no pesa todos los temas igual. Este es tu minimapa de prioridades:

| # | Dominio | Peso | Secciones de esta guía |
|---|---------|------|------------------------|
| 1 | General Security Concepts | 12% | CIA/DAD, Controles, Criptografía |
| 2 | Threats, Vulnerabilities & Mitigations | 22% | Threat Actors, Malware, Cyber Kill Chain, CVSS |
| 3 | Security Architecture | 18% | Redes, Protocolos, BC/DR, Backups |
| 4 | Security Operations | 28% | IAM, Redes, IR, Pen Testing |
| 5 | Security Program Management & Oversight | 20% | Gestión de Riesgos, NIST CSF |

> ⚠️ **Dominio 4 vale más que cualquier otro (28%).** Prioriza IAM, IR y Redes.

---

## 🗓️ PLAN DE REPASO ESPACIADO

La curva del olvido de Ebbinghaus: sin repaso activo, pierdes el 70% del contenido en 24 horas. Este plan lo contrarresta:

| Día | Estudia | Repasa (activo: cubre definición, explícala tú solo) |
|-----|---------|------------------------------------------------------|
| 1 | CIA/DAD + Controles (Secciones 1–3) | — |
| 2 | Threat Actors + Malware (Secciones 4–5) | Día 1 (5 min) |
| 3 | Criptografía + Redes (Secciones 6–8) | Días 1–2 (10 min) |
| 4 | IAM + Kill Chain + NIST CSF + CVSS (Secciones 9–12) | Días 1–3 (15 min) |
| 5 | IR + Riesgos + Backups + BC/DR + Pen Testing (Secciones 13–17) | Días 1–4 (20 min) |
| 7 | — | Todo el documento (1h) |
| 14 | Examen de práctica | Identifica puntos débiles |
| 21 | Examen de práctica | — |

> 🧠 Repaso ≠ releer. Cubre la definición → intenta explicarla en voz alta → descubre → corrígete. Ese esfuerzo es lo que graba la memoria.

---

## 📊 SECCIÓN 1 — CIA TRIAD: LAS TRES ESTADÍSTICAS BASE

> 🧠 **Mnemónica:** CIA protege. DAD destruye. 1vs1.

**Confidentiality** (Confidencialidad)
Solo quien debe ver la información, la ve. Nadie más.
> 🎮 *League of Legends* — La niebla de guerra. El equipo enemigo no puede ver lo que pasa en tu lado del mapa. La información existe, pero está bloqueada para quienes no tienen permiso.
> 💻 El cifrado AES-256 en un disco duro — aunque alguien robe el disco físicamente, no puede leer los datos sin la clave.

**Integrity** (Integridad)
Los datos no han sido modificados por nadie no autorizado. Lo que ves es lo real.
> 🎮 *Minecraft* — Un jugador en supervivencia que usa comandos de trampas (`/give`, modo creativo) para cambiar su inventario sin ganarlo legítimamente. Lo que ves en su inventario ya no refleja la realidad del juego.
> 💻 Un hash SHA-256 en una transferencia de archivos — si el hash del archivo recibido no coincide con el original, sabes que fue alterado en tránsito.

**Availability** (Disponibilidad)
El sistema está accesible cuando se necesita, sin interrupciones.
> 🎮 *League of Legends* — Los servidores de Riot deben estar siempre online. Si caen, el servicio existe pero nadie puede acceder a él.
> 💻 Un clúster de servidores con failover automático — si un nodo cae, el tráfico se redirige al siguiente sin que el usuario lo note.

🔗 **Conecta con:** Los ataques del **DAD Triad** (Sección 2) rompen cada pilar de CIA exactamente uno a uno. Los **Tipos de Control** (Sección 3) son las defensas que los protegen.

---

## ⚔️ SECCIÓN 2 — DAD TRIAD: LOS ATAQUES A LA CIA

> 🧠 **Mnemónica:** "**DAD** destruye a **CIA**" — Disclosure rompe Confidencialidad · Alteration rompe Integridad · Denial rompe Disponibilidad.

**Disclosure** (Revelación) → ataca Confidentiality
Información confidencial expuesta a quien no debería verla.
> 🎮 *League of Legends* — Evelynn invisible recorriendo tu jungla y viendo todos tus movimientos sin que lo notes. Tiene acceso a información que no le corresponde.
> 💻 Un atacante que intercepta tráfico HTTP sin cifrar con Wireshark y lee credenciales en texto plano.

**Alteration** (Alteración) → ataca Integrity
Datos modificados sin autorización, corrompiendo su integridad.
> 🎮 *The Elder Scrolls V: Skyrim* — Usar la consola de comandos (`~`) para añadir oro infinito, cambiar estadísticas o eliminar NPCs que no deberían eliminarse. El estado del mundo ya no refleja nada legítimo.
> 💻 Un ataque Man-in-the-Middle que intercepta y modifica una transferencia bancaria, cambiando el número de cuenta destino antes de que llegue al servidor.

**Denial** (Denegación) → ataca Availability
El servicio es bloqueado y nadie puede usarlo.
> 🎮 *League of Legends* — Un ataque DDoS al servidor de Riot. Miles de conexiones falsas saturan el sistema hasta que nadie puede entrar a ninguna partida.
> 💻 Un ataque DDoS volumétrico que inunda con tráfico basura el ancho de banda de un servidor web hasta dejarlo inaccesible para usuarios legítimos.

🔗 **Conecta con:** Los **Threat Actors** (Sección 4) son quienes ejecutan estos ataques. El **Malware** (Sección 5) es su herramienta principal. El **IR Lifecycle** (Sección 13) es el protocolo de respuesta cuando el ataque ya ocurrió.

---

## 🧊 SECCIÓN 3 — TIPOS DE CONTROL: LAS DEFENSAS

> 🧠 **Mnemónica:** "**P**or **D**ios **C**on **D**iligencia **C**rea **D**isciplina" → Preventive · Detective · Corrective · Deterrent · Compensating · Directive

**Preventive** (Preventivo)
Evita que el ataque ocurra antes de que pase.
> 🎮 *League of Legends* — Poner wards antes del gank. Prevención antes de que el enemigo entre.
> 💻 Un firewall con reglas que bloquean puertos no autorizados antes de que cualquier tráfico malicioso llegue a la red interna.

**Detective** (Detectivo)
Identifica que algo malo está ocurriendo o ya ocurrió.
> 🎮 *Among Us* — La sala de cámaras de seguridad. Desde ahí ves al impostor moverse y actuar, pero no puedes intervenir físicamente. Solo detectas y alertas.
> 💻 Un SIEM que analiza logs y dispara una alerta cuando detecta múltiples intentos fallidos de login en menos de 60 segundos.

**Corrective** (Correctivo)
Minimiza el daño y restaura el sistema después de que el incidente ocurrió.
> 🎮 *League of Legends* — Activar Guardian Angel (GA) al morir y seguir peleando. Corriges la situación tras el golpe.
> 💻 Restaurar un servidor desde un backup limpio después de un ataque de ransomware — el sistema vuelve a operar desde el último punto seguro conocido.

**Deterrent** (Disuasivo)
Desanima al atacante antes de que actúe, sin bloquearlo directamente.
> 🎮 *Dark Souls / Elden Ring* — Un invasor con armas +10 y armadura de boss aparece en tu mundo. Calculas que no tienes ninguna posibilidad y vuelves al menú antes de pelear. El disuasivo funcionó sin bloquear nada.
> 💻 Un cartel de "sistema monitorizado 24/7 — toda actividad queda registrada" en la pantalla de login. Reduce intentos de acceso sin bloquear nada técnicamente.

**Compensating** (Compensatorio)
Alternativa que reemplaza al control principal cuando este no está disponible.
> 🎮 *League of Legends* — Si tu main está baneado, juegas tu secundario. Cumples el mismo objetivo con otro recurso.
> 💻 Si no se puede implementar MFA en un sistema legacy, se añade monitorización intensiva de sesiones y restricción por IP como control alternativo.

**Directive** (Directivo)
Políticas o reglas que indican cómo debe actuar la gente.
> 🎮 *League of Legends* — Las reglas de comportamiento de Riot. Dictan el estándar esperado pero no lo imponen técnicamente.
> 💻 La política de contraseñas de la empresa que obliga a usar mínimo 12 caracteres — no bloquea nada, pero define el estándar obligatorio.

> 🧠 **Tip de examen:** Tipo ≠ Categoría. Un firewall es **Preventive** (tipo) + **Technical** (categoría). Un guardia de seguridad es **Preventive** (tipo) + **Physical** (categoría). El examen combina ambas dimensiones en la misma pregunta.

🔗 **Conecta con:** Cada tipo de control cae dentro de una **Categoría de Control** (sección siguiente). Los controles Technical son la primera línea contra el **Malware** (Sección 5). Los controles Operational son el corazón del **IR Lifecycle** (Sección 13).

---

## 🏷️ SECCIÓN 3B — CATEGORÍAS DE CONTROL

**Technical** (Técnico) — Implementado por software o hardware.
> 🎮 *League of Legends* — Vanguard, el anti-cheat que detecta trampas automáticamente sin intervención humana.
> 💻 Un IPS que bloquea automáticamente una IP que genera tráfico malicioso.

**Managerial** (Gerencial) — Políticas, estrategia y administración del riesgo a nivel directivo.
> 🎮 Esports — El coach definiendo la estrategia de draft antes de la partida. No juega, pero sus decisiones afectan todo el equipo.
> 💻 Un risk assessment trimestral donde el CISO evalúa amenazas, prioriza inversiones y aprueba el presupuesto de controles.

**Operational** (Operacional) — Ejecutado por personas en el día a día, no por software.
> 🎮 *League of Legends* — El shotcaller tomando decisiones en tiempo real durante el teamfight.
> 💻 El equipo de SOC revisando alertas del SIEM cada turno, investigando anomalías y escalando incidentes manualmente.

**Physical** (Físico) — Barreras o controles tangibles en el mundo real.
> 🎮 El net café con puertas cerradas y guardia en la entrada — solo entran los que tienen autorización física.
> 💻 Un data center con lector de tarjeta RFID, cámara en la puerta y jaula de servidores con cerradura.

🔗 **Conecta con:** Los controles Managerial definen las prioridades en **Gestión de Riesgos** (Sección 14). Los controles Physical son la última barrera si fallan los controles de **Redes** e **IAM** (Secciones 8–9).

---

## 🦸 SECCIÓN 4 — THREAT ACTORS: TIPOS DE ENEMIGOS

> 🧠 **Mnemónica:** "**S**olo **H**ackean **O**rganizados **N**aciones, **I**nternas **C**ompiten" → Script Kiddie · Hacktivist · Organized Crime · Nation-State · Insider · Competitor

**Script Kiddie**
Atacante sin habilidades propias que usa herramientas ya creadas por otros.
> 🎮 *League of Legends* — Teemo. Molesto, sin mecánicas avanzadas, usa shrooms prefabricados que cualquiera podría activar.
> 💻 Alguien que descarga Metasploit de GitHub sin entender cómo funciona y lo lanza contra servidores aleatorios buscando vulnerabilidades conocidas.

**Hacktivist** (Hacktivista)
Atacante motivado por una causa política o social, no por dinero.
> 🎮 *League of Legends* — Vi. Su lore gira en torno a luchar por justicia en los Undercity. No ataca por dinero, ataca porque cree que es lo correcto.
> 💻 Anonymous desfigurando la web de un gobierno para protestar contra una ley — el objetivo es visibilidad y presión política, no beneficio económico.

**Organized Crime** (Crimen organizado)
Grupo estructurado con recursos y motivación puramente financiera.
> 🎮 *League of Legends* — Gangplank. Sindicato pirata con organización jerárquica, motivado únicamente por el oro.
> 💻 Un grupo que opera ransomware-as-a-service con desarrolladores, negociadores y lavado de criptomonedas. Estructura empresarial criminal completa.

**Nation-State / APT** (Estado-nación / Amenaza persistente avanzada)
Actor patrocinado por un gobierno, con recursos ilimitados y ataques sostenidos a largo plazo.
> 🎮 *Pokémon* — Mewtwo, creado por el Team Rocket bajo órdenes de Giovanni (gobierno con recursos ilimitados). Diseñado como arma perfecta. No actúa en público — espera el momento exacto para ejecutar con poder devastador y precisión quirúrgica.
> 💻 El grupo Lazarus (Corea del Norte) infiltrando redes de bancos internacionales durante meses sin ser detectado, exfiltrando millones antes de activar el payload final.

**Insider Threat** (Amenaza interna)
La amenaza viene de alguien que ya tiene acceso legítimo dentro de la organización.
> 🎮 *League of Legends* — Singed. Juega en tu equipo pero te tira veneno. Es tu aliado y te daña.
> 💻 Un sysadmin con acceso privilegiado que copia la base de datos de clientes a un USB antes de renunciar, o que sabotea sistemas por resentimiento.

**Competitor** (Competidor)
Actor que busca ventaja competitiva espiando o robando información.
> 🎮 *Team Fortress 2* — El Spy. Se disfraza de un miembro de tu equipo, observa todo lo que haces desde adentro y reporta la inteligencia a la línea enemiga. No destruye nada — extrae.
> 💻 Una empresa que contrata a un ex-empleado de la competencia para obtener acceso a roadmaps, precios o código fuente propietario — espionaje corporativo.

🔗 **Conecta con:** Cada Threat Actor tiene un arsenal de **Malware** (Sección 5) preferido. El **Cyber Kill Chain** (Sección 10) describe cómo cualquiera de estos actores ejecuta un ataque paso a paso. El **CVSS** (Sección 12) mide qué tan peligrosas son las vulnerabilidades que explotan.

---

## 🦠 SECCIÓN 5 — MALWARE: TIPOS DE PLAGAS

> 🧠 **Agrúpalos por comportamiento para no confundirlos:**
> - **Se propagan:** Virus (necesita acción del usuario) · Worm (solo, sin usuario) · Botnet (red controlada)
> - **Se esconden:** Rootkit (en el kernel) · Fileless (en la RAM) · Trojan (bajo disfraz legítimo)
> - **Roban datos:** Spyware · Keylogger · Adware
> - **Destruyen / Bloquean:** Ransomware · Logic Bomb

**Virus**
Se adjunta a archivos existentes y necesita que el usuario lo ejecute para propagarse.
> 🎮 *Minecraft* — Un mod descargado de una fuente no oficial que parece añadir nuevas mecánicas, pero lleva código malicioso oculto. Se activa en el momento en que el jugador lo instala, creyendo que es legítimo.
> 💻 Un archivo .exe adjunto en un correo de phishing — al hacer doble clic, inyecta código en procesos legítimos del sistema como explorer.exe.

**Worm** (Gusano)
Se auto-replica por la red sin necesitar ninguna acción del usuario. Consume recursos y ancho de banda.
> 🎮 *Halo* — El Flood. Una vez que infecta a un solo huésped, se replica y se propaga automáticamente a todos los organismos cercanos. No necesita que nadie haga clic en nada — se expande solo hasta consumir todo.
> 💻 WannaCry propagándose por SMB (puerto 445) — sin que nadie haga clic, salta de máquina en máquina explotando EternalBlue hasta infectar miles de equipos en horas.

**Trojan** (Troyano)
Parece un programa legítimo pero lleva código malicioso oculto adentro.
> 🎮 *League of Legends* — Neeko. Se disfraza de tu ADC aliado y parece completamente confiable hasta que actúa.
> 💻 Un "generador de claves" de software pirata que instala un RAT en segundo plano mientras muestra una clave falsa al usuario.

**Ransomware**
Cifra tus archivos y exige un pago para devolverte el acceso.
> 🎮 *League of Legends* — Mordekaiser. Te secuestra en el Reino de los Muertos. No puedes hacer absolutamente nada hasta que él decida o pagues el precio.
> 💻 LockBit cifrando todos los archivos de un hospital — los médicos no pueden acceder a historiales clínicos hasta pagar el rescate en cripto.

**Rootkit**
Se esconde en el kernel del sistema operativo, invisible para el antivirus y el propio OS.
> 🎮 *League of Legends* — Evelynn antes del nivel 6. Opera en el nivel más profundo del mapa (jungla = kernel), completamente invisible al radar normal. No puede ser detectada con herramientas estándar.
> 💻 Un rootkit que modifica las llamadas al sistema operativo — cuando el antivirus lista procesos, el rootkit filtra su propia entrada de los resultados.

**Spyware**
Roba información sigilosamente sin que el usuario lo note.
> 🎮 *Metal Gear Solid* — Solid Snake en modo sigilo total. Se infiltra en territorio enemigo, observa todo lo que sucede y extrae información crítica sin disparar un solo tiro ni activar ninguna alarma.
> 💻 Un stalkerware en un teléfono que envía GPS, mensajes y capturas de pantalla a un servidor remoto sin ninguna notificación visible para el dueño.

**Adware**
Muestra publicidad no deseada de forma constante. A veces deriva en spyware.
> 🎮 Un launcher de juego gratuito que muestra anuncios cada vez que lo abres y cada vez que terminas una partida — molesto, inevitable, y a veces recopila tus datos en segundo plano.
> 💻 Una extensión de navegador gratuita que inyecta banners en cada página y redirige tus búsquedas a través de sus propios servidores para perfilarte y vender esos datos.

**Keylogger**
Captura cada tecla que el usuario presiona y la envía al atacante.
> 🎮 *Valorant* — Imagina un cliente alternativo modificado que registra silenciosamente todo lo que escribes al loguearte — usuario, contraseña, código de verificación — y lo envía a un servidor externo en tiempo real.
> 💻 Un keylogger de hardware conectado entre el teclado y el PC — captura credenciales físicamente sin dejar rastro en el sistema operativo.

**Fileless Malware** (Malware sin archivos)
Vive únicamente en la RAM. No escribe nada en disco, muy difícil de detectar.
> 🎮 *League of Legends* — Nocturne. Opera en tus pesadillas (RAM), no deja rastro en disco al despertar. Cuando el sistema reinicia (amanece), desaparece sin dejar evidencia.
> 💻 Un payload ejecutado directamente en PowerShell en memoria — no toca el disco, no activa antivirus basados en firmas de archivos, y desaparece al reiniciar el sistema.

**Logic Bomb** (Bomba lógica)
Código dormido que se activa solo cuando se cumple una condición específica.
> 🎮 *League of Legends* — La pasiva de Karthus. El código permanece completamente inactivo mientras vive. En el momento exacto en que muere (condición cumplida = trigger), la habilidad explota automáticamente.
> 💻 Un ex-empleado que deja código en el sistema de nóminas que borra todos los registros si su nombre desaparece de la base de datos de empleados activos.

**Botnet**
Red de computadoras infectadas controladas remotamente por un servidor central (C2 — Command and Control).
> 🎮 *StarCraft* — El Overmind Zerg actúa como C2. Los Zerglings infectados son los nodos de la red — no piensan, solo ejecutan órdenes. Miles de unidades coordinadas obedeciendo a un único centro de comando.
> 💻 Mirai infectando routers y cámaras IP vulnerables para construir una red de cientos de miles de dispositivos que lanzó el DDoS más grande de 2016 contra Dyn.

🔗 **Conecta con:** La **Criptografía** (Sección 6) y la **IAM** (Sección 9) son los principales controles técnicos contra el malware. El **IR Lifecycle** (Sección 13) define qué hacer cuando el malware ya está dentro. El **CVSS** (Sección 12) mide qué tan crítica es la vulnerabilidad que cada uno explota.

---

## 🗝️ SECCIÓN 6 — CRIPTOGRAFÍA

> 🧠 **Mnemónica SAH:** **S**imétrico (1 llave, rápido, AES) · **A**simétrico (par de llaves, lento, RSA/ECC) · **H**ashing (one-way, irreversible, SHA)

**Symmetric Encryption / AES** (Cifrado simétrico)
Una sola llave cifra y descifra. Rápido. Ambas partes comparten el mismo secreto.
> 🎮 *League of Legends* — El código secreto del chat de equipo durante la partida. Solo tu equipo lo conoce. Si alguien externo intercepta la comunicación sin la clave, no entiende nada.
> 💻 AES-256 cifrando el disco de un laptop con BitLocker — una sola clave derivada de tu contraseña cifra y descifra todo el volumen. Sin ella, los datos son ruido aleatorio.

**Asymmetric Encryption / RSA / ECC** (Cifrado asimétrico)
Par de llaves: una pública (todos la tienen) y una privada (solo el dueño). Más lento.
> 🎮 *Dark Souls* — El Fog Gate de un área de PvP. Cualquiera puede cruzar la puerta pública (llave pública), pero solo el host puede invocar o banear jugadores (llave privada). Control asimétrico de quién actúa y quién no.
> 💻 SSH con par de claves — el servidor tiene tu clave pública, tú guardas la privada. El servidor cifra un reto con tu pública, solo tu privada puede descifrarlo y autenticarte sin contraseña.

**Hashing / SHA-256**
Convierte cualquier dato en un valor fijo e irreversible (one-way). No se puede deshacer.
> 🎮 *Portal* — Una vez que el cubo cae al incinerador, no hay vuelta atrás. El proceso es irreversible y siempre produce el mismo resultado dado el mismo input.
> 💻 Las contraseñas en una base de datos se guardan como hashes SHA-256, no en texto plano. Si alguien roba la BD, no puede recuperar la contraseña original — solo comparar hashes.

**Digital Signature** (Firma digital)
Firmás con tu llave privada. Cualquiera con tu llave pública puede verificar que fuiste tú. Garantiza no repudio.
> 🎮 *League of Legends* — Tu historial de partidas en op.gg. Riot firma que tú jugaste esa partida. No puedes decir "yo no fui".
> 💻 Un correo firmado digitalmente con S/MIME — el receptor verifica con tu clave pública que el mensaje vino de ti y no fue modificado en tránsito.

**PKI** (Public Key Infrastructure — Infraestructura de llave pública)
Sistema de autoridades (CA — Certificate Authority · RA — Registration Authority) que emiten y gestionan certificados digitales de identidad.
> 🎮 *The Legend of Zelda* — El Sello de la Familia Real de Hyrule. Solo la familia real puede emitirlo. Cualquier documento sin ese sello es inválido y no puede acreditar identidad ante nadie.
> 💻 DigiCert o Let's Encrypt actuando como CA — emiten certificados TLS que los navegadores confían. Sin ese sello, el navegador muestra "Conexión no segura".

**TLS / HTTPS** (Transport Layer Security)
Canal cifrado entre cliente y servidor. Combina cifrado asimétrico (handshake) y simétrico (datos en tránsito).
> 🎮 *Fortnite* — El bus de combate al inicio de la partida. El trayecto (handshake) establece en qué canal operas y negocia las condiciones. Una vez que caes, operas en un canal propio completamente separado.
> 💻 Tu banco en HTTPS — el handshake TLS negocia las claves con RSA/ECC, y luego toda la sesión viaja cifrada con AES. Wireshark solo ve ruido cifrado.

**Perfect Forward Secrecy** (Secreto perfecto hacia adelante)
Genera una llave nueva por sesión. Si comprometen una sesión pasada, las demás siguen seguras.
> 🎮 *Fortnite* — Cada partida tiene un círculo diferente, una estrategia diferente y un resultado diferente. Que el enemigo sepa cómo ganaste la partida de ayer no le dice nada sobre dónde caerás hoy ni qué ruta tomarás.
> 💻 TLS con ECDHE — cada sesión genera claves efímeras. Si un atacante consigue tu clave privada en el futuro, no puede descifrar sesiones pasadas que haya grabado.

🔗 **Conecta con:** La **PKI y TLS** protegen las comunicaciones en **Redes** (Sección 8). El **Hashing** es la base de la autenticación en **IAM** (Sección 9). La **Firma Digital** garantiza el no repudio que se registra en los logs de Accounting.

---

## 🔑 SECCIÓN 6B — TABLA DE ALGORITMOS

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

## 🌐 SECCIÓN 7 — PROTOCOLOS DE RED Y WIRELESS

> 🧠 **Mnemónica WEP → WPA3:** "De madera a acero a bóveda" — cada generación es exponencialmente más fuerte.

### Wireless Security

**WEP** (Wired Equivalent Privacy) — ❌ ROTO
El primer intento de cifrar WiFi. IVs cortos y reutilizados hacen que sea crackeable en minutos.
> 🎮 *Minecraft* — Una puerta de madera en tu base. Parece protección, pero cualquiera con un hacha la rompe en segundos. No uses WEP ni en un museo.
> 💻 Herramientas como Aircrack-ng pueden romper WEP capturando suficientes IVs en minutos.

**WPA2** (WiFi Protected Access 2) — ✅ Mínimo aceptable
Usa AES-CCMP. Vulnerable a ataques de diccionario si la contraseña es débil.
> 🎮 *Minecraft* — Puerta de hierro con palanca. Sólida, pero si alguien conoce la combinación (contraseña débil), entra sin problema.
> 💻 WPA2-Enterprise con RADIUS añade autenticación por certificado individual — mucho más fuerte que la clave compartida de WPA2-Personal.

**WPA3** (WiFi Protected Access 3) — ✅ Estándar actual
Usa SAE (Simultaneous Authentication of Equals) en lugar del handshake de 4 vías. Añade forward secrecy.
> 🎮 *Minecraft* — Puerta de hierro en fortaleza de End Stone Brick reforzada. Incluso si alguien graba tu proceso de apertura (captura el handshake), no puede derivar la clave de los datos capturados.
> 💻 SAE elimina los ataques de diccionario offline — aunque captures el handshake, no puedes crackearlo sin acceso real al AP.

### Protocolos de Transferencia Segura

**SFTP** (SSH File Transfer Protocol) — ⚠️ NO es FTP con SSL. Es un protocolo completamente distinto.
Transferencia de archivos a través de SSH (puerto 22). Todo viaja dentro del túnel SSH.
> 🎮 *Splinter Cell* — Sam Fisher llevando documentos clasificados a través de los conductos subterráneos del edificio (túnel SSH). Todo el trayecto es invisible y cifrado desde el inicio.
> 💻 SFTP cifra tanto la autenticación como los datos. Usa un solo puerto (22). Opción preferida en entornos Unix/Linux.

**FTPS** (FTP Secure / FTP over TLS) — Es FTP tradicional + una capa TLS encima.
Puerto 21 o 990. El protocolo base es FTP, solo el canal está cifrado con TLS.
> 🎮 *Fortnite* — Una llanta blindada que hace exactamente el mismo recorrido de siempre (FTP), pero con armadura TLS instalada por encima. El vehículo es el mismo, solo el blindaje es nuevo.
> 💻 FTPS puede ser Explicit (STARTTLS en puerto 21) o Implicit (TLS desde conexión en puerto 990). Requiere gestión de múltiples puertos para modo pasivo, lo que complica firewalls.

> ⚠️ **Tip de examen — trampa clásica:** SFTP ≠ FTPS. Protocolos distintos, puertos distintos, arquitecturas distintas. El examen los usa como opción de distracción.

### IPsec

**IPsec** (Internet Protocol Security)
Suite de protocolos que añade autenticación y/o cifrado a nivel de capa de red (IP).

**AH** (Authentication Header) — Autentica, garantiza integridad. **No cifra.**
> 🎮 Precinto de seguridad en un paquete. Confirma que el contenido no fue alterado y que viene del remitente correcto, pero el contenido puede verse.
> 💻 Verifica origen e integridad del paquete IP, pero el payload sigue siendo legible.

**ESP** (Encapsulating Security Payload) — Cifra + Autentica. Más completo que AH.
> 🎮 Caja fuerte dentro del paquete. El contenido está cifrado Y autenticado. Nadie puede leer ni modificar el payload.
> 💻 Lo más usado en VPNs. Cifra el payload, autentica el paquete. Combinación estándar.

**Tunnel Mode** — Cifra el paquete IP completo, incluyendo headers. Usado en VPNs site-to-site.
> 🎮 El camión blindado lleva la carga más el camión original dentro de otro camión mayor. Nadie ve origen ni destino real.

**Transport Mode** — Solo cifra el payload; los headers IP son visibles. Usado entre hosts directos.
> 🎮 Solo la carga está en la caja fuerte. El camión (headers) sigue visible.

> 🧠 **Tip de examen:** Tunnel Mode = site-to-site VPN. Transport Mode = host-to-host.

🔗 **Conecta con:** WPA3 y TLS son la base para proteger **Redes** (Sección 8). Un protocolo wireless débil (WEP) es un vector de entrada directo para los **Threat Actors** (Sección 4) durante la fase de Delivery del **Cyber Kill Chain** (Sección 10).

---

## 🌐 SECCIÓN 8 — REDES: EL MAPA

**DMZ** (Demilitarized Zone — Zona desmilitarizada)
Subred pública separada de la red interna. Aloja servidores accesibles desde internet.
> 🎮 *League of Legends* — La calle (lane). Zona pública donde todos pelean, aislada de tu base. Que el enemigo tome la lane no significa que haya tomado tu nexo.
> 💻 El servidor web de una empresa en la DMZ — accesible desde internet, pero si es comprometido, el firewall interno impide que el atacante salte a la red corporativa.

**Firewall**
Filtra el tráfico de red según reglas definidas. Distintos niveles de inspección según el tipo.
> 🎮 *League of Legends* — Las torretas. Distintos niveles de protección, pero todas filtran qué puede pasar y qué no.
> 💻 Un firewall perimetral con reglas ACL que bloquea todo el tráfico entrante excepto los puertos 443 (HTTPS) y 22 (SSH) hacia servidores específicos.

**Packet-Filtering Firewall**
Bloquea o permite por IP, puerto y protocolo. Sin memoria de conexiones.
> 🎮 *LoL* — Torreta Tier 1. Bloquea lo que pasa por delante, pero no recuerda si ese minion ya había pasado antes. Sin estado.
> 💻 Una ACL en un router Cisco que permite solo puertos 80 y 443 — evalúa cada paquete individualmente, sin contexto de sesión.

**Stateful Inspection Firewall**
Recuerda el estado de las conexiones activas para decisiones más inteligentes.
> 🎮 *LoL* — Torreta Tier 2. Recuerda que ese minion ya pasó antes y ajusta la respuesta según el contexto de la oleada completa.
> 💻 Permite respuestas a conexiones iniciadas desde adentro — si llega un paquete sin handshake TCP previo, lo bloquea.

**NGFW** (Next-Generation Firewall)
Deep packet inspection + IDS/IPS + anti-malware integrados en un solo dispositivo.
> 🎮 *LoL* — Torreta + visión verdadera + inhibidor combinados. Ve todo el payload, analiza el contenido real y bloquea amenazas avanzadas.
> 💻 Palo Alto NGFW inspeccionando HTTPS cifrado, identificando la aplicación (no solo el puerto), detectando firmas de malware en el payload y bloqueando en tiempo real.

**IDS** (Intrusion Detection System)
Monitorea y alerta sobre actividad sospechosa. Solo detecta, no bloquea.
> 🎮 *Among Us* — Las cámaras de seguridad. Desde la sala de cámaras puedes ver qué está pasando en cada habitación, pero no puedes intervenir. Solo detectas y alertas al equipo.
> 💻 Snort en modo IDS — genera alertas en el SIEM cuando detecta patrones de escaneo de puertos o firmas de exploit, pero no corta ninguna conexión.

**IPS** (Intrusion Prevention System)
Detecta y bloquea activamente el tráfico malicioso en tiempo real. Está en el path del tráfico.
> 🎮 *Overwatch* — Reinhardt con su barrera activa. No solo alerta cuando los proyectiles vienen — los bloquea físicamente antes de que lleguen a sus compañeros. Está en la línea de fuego.
> 💻 Snort en modo IPS inline — cuando detecta un exploit conocido, descarta el paquete antes de que llegue al servidor destino.

**VPN** (Virtual Private Network)
Crea un túnel cifrado para comunicación segura a través de redes públicas.
> 🎮 *Splinter Cell* — Sam Fisher moviéndose por territorio enemigo a través de conductos de ventilación y rutas subterráneas ocultas. Para el enemigo, no existe. Llega a su destino completamente indetectable.
> 💻 Un empleado remoto conectándose por OpenVPN — todo su tráfico viaja cifrado hasta el gateway corporativo. Para el ISP solo es ruido cifrado hacia una IP.

**NAC** (Network Access Control)
Verifica que un dispositivo cumple requisitos de seguridad antes de dejarlo entrar a la red.
> 🎮 *League of Legends* — El anti-cheat al iniciar partida. Si el sistema no cumple los requisitos (Vanguard activo, versión correcta), no te deja entrar.
> 💻 Cisco ISE verificando antes de dar acceso a la LAN corporativa — si el equipo no tiene antivirus actualizado, parches al día y certificado de dominio, lo manda a una VLAN de cuarentena.

**NAT** (Network Address Translation)
Traduce IPs privadas a una o varias IPs públicas. Permite que múltiples dispositivos compartan una sola IP pública.
> 🎮 Gaming house — Varios jugadores comparten una sola conexión. El router usa NAT para asignar a cada jugador un puerto único bajo una sola IP pública. Cuando Riot responde, el router lee el puerto específico para saber a qué jugador entregarle los datos. El Mid y el ADC juegan simultáneamente sin que sus conexiones se mezclen.
> 💻 Cuando una PC local envía un paquete, el router reemplaza su IP privada por la IP pública y registra la equivalencia en una tabla de traducción. Al recibir la respuesta, consulta esa tabla para reenviar al dispositivo correcto.

**DNS** (Domain Name System — Sistema de nombres de dominio)
Traduce nombres de dominio legibles (google.com) en direcciones IP numéricas (142.250.190.46) que las máquinas pueden enrutar. Es la agenda telefónica de internet.
> 🎮 *Pokémon* — El Centro Pokémon en cada ciudad actúa como un DNS local. No necesitas saber las coordenadas exactas en el mapa. Le dices "Centro Pokémon de Pueblo Paleta" y el sistema lo localiza automáticamente. El nombre es para ti; las coordenadas son para el motor del juego.
> 💻 Cuando escribes `google.com` en el navegador, tu OS consulta un servidor DNS que devuelve la IP 142.250.190.46. Sin DNS, tendrías que memorizar la dirección IP de cada sitio que quieras visitar.

> ⚠️ **Ataques relacionados:** DNS Spoofing/Poisoning — el atacante falsifica la respuesta DNS para redirigirte a una IP maliciosa aunque hayas escrito el dominio correcto.

**SIEM** (Security Information and Event Management)
Centraliza logs de toda la red, correlaciona eventos entre fuentes y genera alertas de seguridad.
> 🎮 *Rainbow Six Siege* — El mapa táctico de la sala de operaciones. Recibe feeds simultáneos de todas las cámaras, drones y sensores acústicos. Correlaciona lo que ve la cámara 1 con el sonido del piso 2 y la imagen del drone exterior. Un solo dato no confirma nada — la correlación de los tres juntos revela la amenaza.
> 💻 Splunk correlacionando logs de firewall, AD, endpoints y proxies — detecta que el mismo usuario falló login 50 veces en 2 minutos desde una IP en Rusia y dispara una alerta crítica.

**SOAR** (Security Orchestration, Automation and Response)
Automatiza la respuesta a incidentes sin intervención manual.
> 🎮 *League of Legends* — Vi con su combo Q→AA→E→R. Una vez iniciado, la secuencia se ejecuta automáticamente sin intervención adicional.
> 💻 Palo Alto XSOAR recibiendo una alerta de phishing — automáticamente bloquea el dominio en el proxy, aísla el endpoint, abre un ticket en Jira y notifica al analista, todo en segundos.

**Load Balancer** (Balanceador de carga)
Distribuye el tráfico entre varios servidores para evitar que uno se sature.
> 🎮 El matchmaking de cualquier juego online — distribuye jugadores entre servidores según carga para que ninguno explote.
> 💻 Un F5 BIG-IP distribuyendo peticiones HTTP entre 10 servidores web — si uno llega al 90% de CPU, el balanceador deja de enviarle tráfico automáticamente.

**Proxy**
Actúa como intermediario entre un cliente y un servidor externo. Inspecciona y filtra el tráfico saliente.
> 🎮 *League of Legends* — El proxy farming de Singed. Se posiciona entre el enemigo y su torreta, absorbiendo la atención y canalizando el tráfico a través de su posición.
> 💻 Un proxy corporativo (Zscaler) por el que sale todo el tráfico web de los empleados — inspecciona URLs, aplica filtros de contenido y registra cada petición antes de reenviarla a internet.

**ACL** (Access Control List — Lista de control de acceso)
Lista de reglas ordenadas que permiten o deniegan tráfico. Se procesan de arriba hacia abajo. Primera coincidencia gana.
> 🎮 *LoL* — El sistema de mute y restricciones de chat. La primera regla que coincide se aplica. Si el jugador está en lista negra, la regla superior deniega antes de evaluar las demás.
> 💻 Una ACL en un switch que permite tráfico del VLAN 10 al servidor de archivos en el puerto 445, deniega todo lo demás, procesando las reglas de arriba a abajo hasta encontrar un match.

🔗 **Conecta con:** El **IDS** alimenta el **SIEM** con alertas. El **SOAR** automatiza la respuesta que definiría el **IR Lifecycle** (Sección 13). La **DMZ** es parte de la arquitectura que protege la **Confidentiality** de la CIA Triad (Sección 1). Los firewalls son controles **Technical + Preventive** de las Secciones 3 y 3B.

---

## 🔐 SECCIÓN 9 — IAM: ROLES Y PERMISOS

> 🧠 **Mnemónica de acceso:** "**I**dentifícate → **A**utentica → **A**utoriza → **A**udita" — Las 4 A del control de acceso

**Identification** (Identificación)
Declarar quién eres ante el sistema. Sin probar nada todavía.
> 🎮 *League of Legends* — Pickear campeón en champ select. Declaras quién eres en esta partida, pero todavía no has demostrado nada.
> 💻 Escribir tu nombre de usuario en el campo de login — el sistema sabe a quién buscar, pero no ha verificado nada.

**Authentication** (Autenticación)
Probar que eres quien dices ser.
> 🎮 *League of Legends* — Loguearte al cliente de Riot. Demuestras que eres el dueño real de esa cuenta.
> 💻 Introducir tu contraseña o pasar un desafío de MFA — el sistema valida que tienes el secreto que solo el dueño legítimo debería tener.

**Authorization** (Autorización)
Qué tienes permiso de hacer una vez que tu identidad fue verificada.
> 🎮 *League of Legends* — El rol asignado en champ select. Mid no toca la jungla. Cada rol tiene sus límites definidos.
> 💻 Un developer autenticado que puede leer el repositorio de código pero no puede hacer push a main — credenciales válidas, pero permisos limitados por rol.

**Accounting / Audit** (Contabilidad / Auditoría)
Registro de todo lo que hiciste en el sistema. Trazabilidad total.
> 🎮 *League of Legends* — El post-game lobby. KDA, daño, wards, todo queda registrado y no se puede borrar.
> 💻 Los logs de Active Directory registrando cada inicio de sesión, cada cambio de permiso y cada acceso a un recurso — si hay un incidente, el forense reconstruye exactamente qué pasó y cuándo.

**MFA** (Multi-Factor Authentication — Autenticación multifactor)
Verificación con dos o más factores de categorías distintas (no basta con dos contraseñas).
> 🎮 *World of Warcraft* — El autenticador físico de Blizzard. Contraseña (algo que sabes) + código del dispositivo físico (algo que tienes) = dos factores de categorías distintas.
> 💻 Login con contraseña + código TOTP de Google Authenticator. Si roban la contraseña, sin el teléfono no pueden entrar.

**RBAC** (Role-Based Access Control)
Los permisos se asignan por rol, no por usuario individual.
> 🎮 *League of Legends* — ADC farmea, Supp protege, Jungler smitea. Cada rol tiene acciones definidas y no invade las del otro.
> 💻 En Azure AD, el rol "Reader" puede ver recursos pero no modificarlos. El acceso se hereda del rol, no se configura por persona.

**ABAC** (Attribute-Based Access Control)
El acceso depende de condiciones o atributos específicos del usuario, entorno y recurso.
> 🎮 *World of Warcraft* — Sistema de gear score para raids. Solo puedes entrar si tu item level supera X, eres de la guild correcta y estás en el servidor PvE. Los tres atributos deben cumplirse simultáneamente.
> 💻 Política que permite acceso a documentos clasificados solo si: el usuario es del departamento Legal, está en la red corporativa y el documento tiene clasificación ≤ Confidential.

**MAC** (Mandatory Access Control)
El sistema impone los niveles de acceso. El usuario no puede cambiarlos aunque quiera.
> 🎮 *Pokémon* — El sistema de Insignias de Gimnasio. No importa lo fuerte que sea tu equipo — sin la Insignia Trueno no puedes acceder al Gimnasio de Ciudad Azulona. El sistema decide el acceso, no el jugador.
> 💻 SELinux en un servidor Linux — el sistema operativo impone etiquetas de seguridad a cada proceso. Ni el root puede acceder fuera de su etiqueta definida por política.

**DAC** (Discretionary Access Control)
El dueño del recurso decide quién puede acceder.
> 🎮 *League of Legends* — El que hostea la custom game decide quién entra y con qué equipo.
> 💻 El propietario de una carpeta compartida en Windows que decide qué usuarios o grupos tienen lectura o escritura.

**SSO** (Single Sign-On — Inicio de sesión único)
Una sola autenticación da acceso a múltiples sistemas del ecosistema.
> 🎮 Cuenta de Google — un solo login da acceso a Gmail, YouTube, Google Drive y Google Docs. Una autenticación, múltiples servicios.
> 💻 Okta SSO en una empresa — el empleado se autentica una vez y accede sin volver a loguearse a Slack, Salesforce, GitHub y Jira.

**Federation** (Federación)
Dos organizaciones distintas se confían mutuamente para compartir identidad de usuarios.
> 🎮 *Fortnite* — Las colaboraciones crossover con Marvel, Star Wars o Dragon Ball. Tu identidad de jugador de Fortnite es reconocida por el ecosistema de la colaboración sin crear una cuenta nueva en cada universo.
> 💻 Azure AD federado con el AD de un partner externo — el empleado del partner se autentica con sus propias credenciales y accede a recursos compartidos sin una cuenta adicional.

**Least Privilege** (Mínimo privilegio)
Cada usuario solo tiene los permisos mínimos necesarios para su función, nada más.
> 🎮 *League of Legends* — El supp no toma el blue buff. Solo usa los recursos estrictamente necesarios para su rol.
> 💻 Una cuenta de servicio con solo permisos de lectura sobre la tabla de BD que necesita — si esa cuenta es comprometida, el atacante no puede escribir, borrar ni acceder a otras tablas.

**PAM** (Privileged Access Management — Gestión de acceso privilegiado)
Control especial sobre cuentas con permisos elevados. Incluye logs, MFA extra y tiempo limitado.
> 🎮 Esports profesional — Las credenciales de administrador del equipo de gestión. Solo el manager puede hacer cambios de roster, con verificación adicional y registro de cada acción tomada.
> 💻 CyberArk gestionando cuentas de admin — las contraseñas root rotan automáticamente, cada sesión privilegiada queda grabada en video, y el acceso expira después de un tiempo definido.

🔗 **Conecta con:** Un fallo de IAM (contraseña débil, permisos excesivos) es el vector de entrada más común para los **Threat Actors** (Sección 4). La revocación de credenciales en la fase de **Containment** del IR (Sección 13) es el control de IAM más crítico durante un incidente.

---

## 💣 SECCIÓN 10 — CYBER KILL CHAIN: LA CADENA DE ATAQUE

> 7 fases que cualquier ataque sofisticado sigue desde el inicio hasta el objetivo final. Cortar la cadena en cualquier fase detiene el ataque.
> 🧠 **Mnemónica:** "**R**econ **W**eaponize **D**eliver **E**xploit **I**nstall **C**2 **A**ct" → RWDEICA

| Fase | Nombre | 🎮 Esports / LoL | 💻 IT Real |
|------|--------|-----------------|-----------|
| 1 | **Reconnaissance** | Ver VODs del equipo rival, estudiar su draft y rutas de jungler | Escaneo de puertos (Nmap), OSINT en LinkedIn, análisis de subdominios |
| 2 | **Weaponization** | Preparar el draft contra-pick y definir la estrategia de teamfight | Combinar un exploit con un RAT para crear el malware específico |
| 3 | **Delivery** | Ejecutar el pick en champ select — el arma ya está en el campo | Correo de phishing, USB abandonado, watering hole attack |
| 4 | **Exploitation** | El pick explota la debilidad de la comp enemiga en el teamfight | CVE ejecutado, vulnerabilidad activada en el sistema objetivo |
| 5 | **Installation** | Establecer control de visión y objetivos en el mapa | Instalar backdoor, crontab malicioso, scheduled task persistente |
| 6 | **Command & Control (C2)** | El jungler dictando calls desde la ventaja de objetivos | El malware beaconea al servidor C2 del atacante para recibir órdenes |
| 7 | **Actions on Objectives** | Tomar el Nexus | Exfiltrar datos, cifrar con ransomware, destruir infraestructura |

> 🛡️ **Por qué importa:** Mejor cortar en fase 1–2 (Recon/Weaponize = detección temprana) que en fase 6–7 (ya hay daño). Los controles Preventive cortan las fases tempranas. Los Corrective actúan en las tardías.

🔗 **Conecta con:** Los **Threat Actors** (Sección 4) siguen esta cadena. Los **Controles** (Sección 3) están diseñados para interrumpirla en cada fase. El **NIST CSF** (Sección 11) organiza defensas que mapean a cada fase del Kill Chain.

---

## 🛡️ SECCIÓN 11 — NIST CSF: EL FRAMEWORK DE CIBERSEGURIDAD

> El NIST Cybersecurity Framework es el estándar de gestión de riesgos más usado en EE.UU. No es una ley — es un marco de referencia para organizar defensas.
> 🧠 **Mnemónica:** "**I**ntenta **P**roteger **D**onde **R**eal **R**iesgo" → Identify · Protect · Detect · Respond · Recover

| Función | Descripción | 🎮 Analogía | 💻 Ejemplo real |
|---------|-------------|------------|-----------------|
| **Identify** | Conocer qué activos necesitas proteger | *Minecraft* — Hacer inventario de tus chests antes de construir la base: qué tienes, dónde está, qué vale proteger | Inventario de activos (CMDB), análisis de riesgo, clasificación de datos |
| **Protect** | Implementar controles para proteger esos activos | *Minecraft* — Construir muros, poner antorchas contra mobs, instalar puerta de hierro | Firewalls, MFA, cifrado, políticas de acceso, security awareness training |
| **Detect** | Identificar que algo malo está ocurriendo | *Among Us* — El equipo empieza a notar comportamientos anómalos del impostor: tareas que nadie completó, reportes de cadáveres | IDS, SIEM, monitorización de endpoints, análisis de logs |
| **Respond** | Actuar cuando se detecta una amenaza | *Among Us* — Votación de emergencia, discusión del equipo, contención del impostor (o el crewmate equivocado) | IR Plan, aislamiento de sistemas, notificación a stakeholders, análisis forense |
| **Recover** | Restaurar operaciones normales con seguridad | *Minecraft* — Reconstruir lo que destruyeron, mejorar las defensas y volver a jugar con el conocimiento de lo que falló | Restauración desde backups, hardening post-incidente, documentación de lecciones aprendidas |

🔗 **Conecta con:** El **NIST CSF** es el paraguas que organiza todos los controles de esta guía. Detect = **Detective Controls** (Sección 3) + **SIEM** (Sección 8). Respond = **IR Lifecycle** (Sección 13). Recover = **Backups + BC/DR** (Secciones 15–16).

---

## 📊 SECCIÓN 12 — CVSS: MIDIENDO LA SEVERIDAD DE UNA VULNERABILIDAD

**CVSS** (Common Vulnerability Scoring System)
Sistema estándar para cuantificar la severidad de una vulnerabilidad del 0 al 10. Determina prioridad de parcheo.

| Puntuación | Severidad | 🎮 Analogía de dificultad |
|-----------|-----------|--------------------------|
| 0.0 | None | Modo historia — sin riesgo real |
| 0.1 – 3.9 | Low | Modo fácil — el ataque requiere condiciones muy específicas o acceso físico local |
| 4.0 – 6.9 | Medium | Modo normal — explotable pero con limitaciones claras |
| 7.0 – 8.9 | High | Modo difícil — impacto serio, explotable sin privilegios especiales |
| 9.0 – 10.0 | Critical | Modo Elden Ring sin escudo — explotable remotamente, sin autenticación, impacto total en CIA |

> 🧠 **Qué mide el CVSS:** Vector de ataque (remoto/local) · Complejidad · Privilegios requeridos · Interacción del usuario · Impacto en Confidencialidad, Integridad y Disponibilidad (la CIA Triad).

🔗 **Conecta con:** El CVSS es la métrica que usa la **Gestión de Riesgos** (Sección 14) para priorizar parches. Un CVE con CVSS 9.8 es exactamente lo que un attackante busca durante la fase de **Reconnaissance** del Cyber Kill Chain (Sección 10).

---

## 🚑 SECCIÓN 13 — INCIDENT RESPONSE: EL PROTOCOLO DE EMERGENCIA

> 🧠 **Mnemónica PICREL:** **P**reparation · **I**dentification · **C**ontainment · **E**radication · **R**ecovery · **L**essons Learned

**Preparation** (Preparación)
Todo listo antes del incidente: herramientas, planes, equipo entrenado.
> 🎮 *League of Legends* — Pick/Ban + Runas configuradas antes de empezar. El equipo ya sabe qué hacer cuando empiece la partida.
> 💻 Tener el playbook de IR documentado, el SIEM configurado, los backups verificados y el equipo SOC con tabletop exercises — todo antes del primer incidente real.

**Identification** (Identificación)
Detectar que el incidente está ocurriendo usando logs, alertas e IoCs (Indicators of Compromise).
> 🎮 *League of Legends* — "¡Mid mia!" El jungler enemigo aparece en el minimapa. El ataque fue detectado.
> 💻 El SIEM dispara una alerta por tráfico de C2 beaconing hacia una IP en lista negra — el analista confirma que es un incidente real, no un falso positivo, y lo declara formalmente.

**Containment** (Contención)
Limitar el daño. Aislar el sistema comprometido sin eliminar la amenaza todavía.
> 🎮 *League of Legends* — Flash + barrera y ponerse bajo torreta. Limitas el daño y te pones a salvo antes de contraatacar.
> 💻 Aislar el endpoint infectado en una VLAN de cuarentena y revocar sus credenciales — el malware queda atrapado sin poder comunicarse con el C2 ni moverse lateralmente.

**Eradication** (Erradicación)
Eliminar la amenaza por completo del sistema.
> 🎮 *League of Legends* — Focus y eliminar al carry enemigo. Limpias la amenaza de raíz.
> 💻 Reimagear el endpoint desde golden image, parchear la vulnerabilidad explotada y eliminar todas las cuentas y backdoors creados por el atacante.

**Recovery** (Recuperación)
Restaurar las operaciones normales de forma segura.
> 🎮 Cualquier juego competitivo — Respawn, TP a lane y vuelves a operar con normalidad restaurada.
> 💻 Restaurar el servidor desde backup limpio, verificar integridad de datos y monitorear intensivamente durante 72 horas antes de declarar el sistema operativo.

**Lessons Learned** (Lecciones aprendidas)
Post-mortem: qué salió mal, qué mejorar para el siguiente incidente.
> 🎮 Cualquier juego competitivo — El post-game review. Analizas la partida completa para no repetir los mismos errores.
> 💻 Reunión post-incidente donde el equipo documenta la línea de tiempo del ataque, identifica qué control falló y actualiza el playbook y las reglas del SIEM.

🔗 **Conecta con:** El IR Lifecycle es la respuesta operativa a los ataques del **Cyber Kill Chain** (Sección 10). Los **Backups** (Sección 15) son la base del Recovery. La fase Preparation incluye tener un **SIEM** configurado (Sección 8) y definir la **Gestión de Riesgos** (Sección 14).

---

## 📋 SECCIÓN 14 — GESTIÓN DE RIESGOS

> 🧠 **Fórmula clave:** SLE × ARO = ALE

**SLE** (Single Loss Expectancy — Pérdida esperada por evento único)
Cuánto pierdes económicamente si el incidente ocurre una sola vez.
> 🎮 El gold que pierdes si mueres una vez.
> 💻 Si un servidor de producción cae, SLE = coste por hora de downtime × horas de recuperación + daño reputacional estimado.

**ARO** (Annual Rate of Occurrence — Tasa anual de ocurrencia)
Cuántas veces se espera que ocurra el incidente en un año.
> 🎮 Cuántas veces mueres por partida en promedio.
> 💻 Si el servidor ha caído 3 veces en 2 años, ARO = 1.5. Se basa en datos históricos o tablas actuariales del sector.

**ALE** (Annual Loss Expectancy — Pérdida anual esperada) = SLE × ARO
El impacto económico total que ese riesgo genera en un año completo.
> 🎮 SLE × ARO = gold perdido total en toda la temporada.
> 💻 SLE de $50,000 × ARO de 1.5 = ALE de $75,000. Si un control cuesta $20,000/año y reduce el ARO a 0.5, el ALE baja a $25,000 — el control se justifica económicamente.

**RTO** (Recovery Time Objective — Objetivo de tiempo de recuperación)
Cuánto tiempo máximo puede estar caído el sistema antes de restaurarlo.
> 🎮 Cuánto tardas en revivir y volver a lane.
> 💻 RTO = 4 horas — si el sistema de pagos cae, tienes 4 horas para restaurarlo antes de incumplir el SLA y enfrentar penalizaciones.

**RPO** (Recovery Point Objective — Objetivo de punto de recuperación)
Cuánta información puedes permitirte perder, medida en tiempo hacia atrás.
> 🎮 Cuánto XP y gold perdiste desde el último checkpoint de guardado.
> 💻 RPO = 1 hora significa backups cada hora — como máximo pierdes 60 minutos de transacciones. Si RPO = 0, necesitas replicación en tiempo real.

🔗 **Conecta con:** ALE determina cuánto gastar en controles — si el control cuesta más que el ALE, no se justifica. RTO y RPO definen los requisitos para **Backups** y **Sitios de Contingencia** (Secciones siguientes). El **CVSS** (Sección 12) alimenta la evaluación del impacto en el SLE.

---

## 💾 SECCIÓN 15 — BACKUPS: EL SISTEMA DE REPLAY

> 🧠 **Mnemónica FID:** **F**ull (todo, lento de hacer, rápido de restaurar) · **I**ncremental (desde el último backup, rapidísimo pero restaurar requiere encadenar) · **D**ifferential (desde el último Full, medio en ambos)

| Tipo | Velocidad backup | Velocidad restore | 🎮 Videojuegos | 💻 IT Real |
|------|-----------------|------------------|----------------|-----------|
| **Full** | Lenta | Rápida | Guardar el replay completo de la partida desde minuto 0 | Snapshot completo de la VM — restaurar es directo, pero ocupa mucho espacio |
| **Incremental** | Rápida | Lenta | Solo los últimos 5 minutos desde el backup anterior | Solo bloques cambiados desde el último backup — restaurar requiere encadenar todos los incrementales |
| **Differential** | Media | Media | Todo desde el último Full guardado | Cambios desde el último Full — restaurar necesita el Full + el último Differential |

**Regla 3-2-1:** 3 copias de datos · en 2 tipos de medios distintos · 1 copia fuera del sitio (offsite o cloud).

---

## 🏗️ SECCIÓN 16 — SITIOS DE CONTINGENCIA (BC/DR)

> 🧠 **Mnemónica:** Hot = Challenger listo (segundos) · Warm = Diamante calentando (horas) · Cold = Nivel 30 sin ranked (días)

**Hot Site** — Réplica exacta y activa del sistema. Activación en segundos.
> 🎮 *League of Legends* — Tener un smurf en Challenger listo para jugar. Sin warm-up, entra directo a rendir al máximo.
> 💻 Datacenter secundario con servidores encendidos y datos replicados en tiempo real — si el primario cae, el secundario asume en segundos sin intervención manual.

**Warm Site** — Infraestructura parcialmente lista. Necesita configuración. Horas.
> 🎮 *League of Legends* — Una cuenta en Diamante. Lista pero necesita unas partidas de calentamiento antes de rendir al máximo.
> 💻 Servidores preinstalados en el site secundario pero sin datos actualizados — al activarse hay que restaurar los últimos backups y configurar las aplicaciones antes de redirigir el tráfico.

**Cold Site** — Solo espacio físico e infraestructura básica. Instalación completa. Días.
> 🎮 *League of Legends* — Cuenta nivel 30 sin ranked. Tienes la base, pero hay que grindear todo desde cero.
> 💻 Sala de datacenter con racks vacíos y electricidad — hay que instalar hardware, OS, restaurar backups y reconfigurar todo antes de poder operar.

---

## 🔍 SECCIÓN 17 — PEN TESTING: TIPOS DE PRUEBA

**Black Box** (Caja negra) — Sin conocimiento previo del sistema objetivo.
> 🎮 Jugar contra un equipo desconocido en un torneo. No sabes su composición, sus rutas ni su estilo de juego.
> 💻 Un pentester externo que solo recibe el nombre del dominio — simula exactamente lo que haría un atacante real sin información privilegiada.

**White Box** (Caja blanca) — Acceso completo: código fuente, arquitectura, credenciales, documentación.
> 🎮 Ver el replay completo del enemigo antes del match. Conoces cada decisión que tomaron, su build, sus runas y sus patrones.
> 💻 Un auditor con acceso al código fuente, diagramas de red y credenciales de admin — puede revisar lógica de negocio y vulnerabilidades solo visibles desde adentro.

**Gray Box** (Caja gris) — Conocimiento parcial del sistema.
> 🎮 *CS:GO / Valorant* — Sabes qué agente juega el mid enemigo pero no conoces sus estadísticas, su loadout ni sus rutas preferidas.
> 💻 Un pentester con credenciales de usuario estándar pero sin acceso admin — simula a un atacante que ya comprometió una cuenta de bajo privilegio y busca escalar.

---

## 📊 TABLA RESUMEN — CHEAT CODES

| Concepto | Fórmula / Frase clave |
|----------|----------------------|
| **CIA** | Confidentiality · Integrity · Availability |
| **DAD** | Disclosure (→C) · Alteration (→I) · Denial (→A) — cada uno destruye un pilar de CIA |
| **Control Types** | Preventive · Detective · Corrective · Deterrent · Compensating · Directive |
| **Control Categories** | Technical · Managerial · Operational · Physical |
| **Threat Actors (SHONIC)** | Script Kiddie · Hacktivist · Organized Crime · Nation-State · Insider · Competitor |
| **Malware (propagan)** | Virus (usuario) · Worm (solo, sin clic) · Botnet (red C2) |
| **Malware (esconden)** | Rootkit (kernel) · Fileless (RAM) · Trojan (disfraz legítimo) |
| **Malware (roban)** | Spyware · Keylogger · Adware |
| **Malware (destruyen)** | Ransomware · Logic Bomb |
| **Crypto SAH** | Simétrico = AES (1 llave, rápido) · Asimétrico = RSA/ECC (par, lento) · Hashing = SHA (one-way) |
| **Hashing** | One-way. SHA-256 ✅ · MD5/SHA-1 ❌ |
| **IDS vs IPS** | IDS = solo detecta · IPS = detecta + bloquea (inline) |
| **Wireless** | WEP ❌ → WPA2 ⚠️ → WPA3 ✅ (SAE + forward secrecy) |
| **File Transfer** | SFTP = SSH (puerto 22) · FTPS = FTP + TLS (puerto 21/990) · NO son lo mismo |
| **IPsec** | AH (autentica, no cifra) + ESP (cifra + autentica). Tunnel = site-to-site · Transport = host-to-host |
| **AuthN vs AuthZ** | AuthN = ¿Quién eres? · AuthZ = ¿Qué puedes hacer? |
| **RBAC/ABAC/MAC/DAC** | Rol · Atributos condicionales · Sistema impone · Dueño decide |
| **IR Lifecycle (PICREL)** | Preparation → Identification → Containment → Eradication → Recovery → Lessons Learned |
| **Cyber Kill Chain (RWDEICA)** | Recon → Weaponize → Deliver → Exploit → Install → C2 → Act |
| **NIST CSF (IPDRD)** | Identify → Protect → Detect → Respond → Recover |
| **CVSS** | 0 = None · <4 = Low · 4–7 = Medium · 7–9 = High · 9–10 = Critical |
| **SLE / ARO / ALE** | SLE × ARO = ALE |
| **RTO / RPO** | RTO = tiempo máximo caído · RPO = datos máximos que puedes perder |
| **Backup FID** | Full (lento/rápido) · Incremental (rápido/lento) · Differential (medio/medio) |
| **Backup 3-2-1** | 3 copias · 2 medios distintos · 1 offsite |
| **BC/DR Sites** | Hot (segundos) · Warm (horas) · Cold (días) |
| **PKI Flow** | CA emite → RA verifica → Cert vincula identidad → CRL/OCSP chequean validez |
| **Pen Testing** | Black Box (0 info) · Gray Box (info parcial) · White Box (acceso total) |

---

> *"GG. Usa el plan de repaso espaciado como tu rutina de entrenamiento. El cheat sheet es tu pre-game — úsalo para verificar, no para estudiar por primera vez."*
