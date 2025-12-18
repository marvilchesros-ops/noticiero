# Noticiero automático (Python + GitHub Actions)

## Qué hace
- Recolecta titulares y contenido de las fuentes definidas.
- Filtra por palabras clave y por “reciente” (p. ej., últimas 24 h).
- Genera un resumen HTML y lo envía por correo.
- Se ejecuta automáticamente (cron) o bajo demanda desde **Actions**.

---

## Uso para no técnicos (2 pasos)

### 1) Editar la configuración
Abrir `config.yaml` → botón ✏️ → modificar → **Commit changes**.

Ejemplo:
```yaml
keywords:
  - "oro"
  - "pies"

tzname: "Europe/Madrid"
hours_recent: 24

email:
  user: "marvilchesros@gmail.com"   # remitente
  to_emails:
    - "mmvilches@enagas.es"     # destinatarios

sources:
  -
  - name: "20MINUTOS"
    url: https://www.20minutos.es/
    max_to_fetch: 400
  
  - name: "ABC"
    url: https://www.abc.es/
    max_to_fetch: 400
  
  - name: "BOLSAMANIA"
    url: https://www.bolsamania.com/
    max_to_fetch: 400
  
  - name: "CINCO_DIAS"
    url: https://cincodias.elpais.com/
    max_to_fetch: 400
  
  - name: "COMPROMISORSE"
    url: https://www.compromisorse.com/
    max_to_fetch: 400
  
  - name: "CORRESPONSABLES"
    url: https://www.corresponsables.com/
    max_to_fetch: 400
  
  - name: "CRONICA_ECONOMICA"
    url: https://www.cronicaeconomica.com/
    max_to_fetch: 400
  
  - name: "CRONICA_GLOBAL"
    url: https://cronicaglobal.elespanol.com/
    max_to_fetch: 400
  
  - name: "DIARIO_SIGLO_XXI"
    url: https://www.diariosigloxxi.com/
    max_to_fetch: 400
  
  - name: "ECONOMIA_DIGITAL"
    url: https://www.economiadigital.es/
    max_to_fetch: 400
  
  - name: "EFE"
    url: https://www.efe.com/
    max_to_fetch: 400
  
  - name: "EJECUTIVOS"
    url: https://www.ejecutivos.es/
    max_to_fetch: 400
  
  - name: "EL_CONFIDENCIAL"
    url: https://www.elconfidencial.com/
    max_to_fetch: 400
  
  - name: "EL_DEBATE"
    url: https://www.eldebate.com/
    max_to_fetch: 400
  
  - name: "EL_DIARIO"
    url: https://www.eldiario.es/
    max_to_fetch: 400
  
  - name: "EL_ECONOMISTA"
    url: https://www.eleconomista.es/
    max_to_fetch: 400
  
  - name: "EL_PERIODICO_DE_LA_ENERGIA"
    url: https://elperiodicodelaenergia.com/
    max_to_fetch: 400
  
  - name: "EL_PERIODICO"
    url: https://www.elperiodico.com/
    max_to_fetch: 400
  
  - name: "EL_MUNDO"
    url: https://www.elmundo.es/
    max_to_fetch: 400
  
  - name: "EL_PAIS"
    url: https://elpais.com/
    max_to_fetch: 400
  
  - name: "EL_ESPANOL"
    url: https://www.elespanol.com/
    max_to_fetch: 400
  
  - name: "EL_NACIONAL"
    url: https://www.elnacional.cat/
    max_to_fetch: 400
  
  - name: "EPE"
    url: https://www.epe.es/
    max_to_fetch: 400
  
  - name: "EUROPA_PRESS"
    url: https://www.europapress.es/
    max_to_fetch: 400
  
  - name: "EXPANSION"
    url: https://www.expansion.com/
    max_to_fetch: 400
  
  - name: "FINANZAS"
    url: https://www.finanzas.com/
    max_to_fetch: 400
  
  - name: "FORBES"
    url: https://forbes.es/
    max_to_fetch: 400
  
  - name: "HISPANIDAD"
    url: https://www.hispanidad.com/
    max_to_fetch: 400
  
  - name: "LA_RAZON"
    url: https://www.larazon.es/
    max_to_fetch: 400
  
  - name: "LA_VANGUARDIA"
    url: https://www.lavanguardia.com/
    max_to_fetch: 400
  
  - name: "LIBERTAD_DIGITAL"
    url: https://www.libertaddigital.com/
    max_to_fetch: 400
  
  - name: "MERCA2"
    url: https://www.merca2.es/
    max_to_fetch: 400
  
  - name: "OKDIARIO"
    url: https://www.okdiario.com/
    max_to_fetch: 400
  
  - name: "PUBLICO"
    url: https://www.publico.es/
    max_to_fetch: 400
  
  - name: "REUTERS"
    url: https://www.reuters.com/
    max_to_fetch: 400
  
  - name: "RTVE"
    url: https://www.rtve.es/
    max_to_fetch: 400
  
  - name: "SERVIMEDIA"
    url: https://www.servimedia.es/
    max_to_fetch: 400
  
  - name: "THE_OBJECTIVE"
    url: https://theobjective.com/
    max_to_fetch: 400
  
  - name: "VOZPOPULI"
    url: https://www.vozpopuli.com/
    max_to_fetch: 400
  
  # ANDALUCIA
  - name: "DIARIO_DE_SEVILLA_ANDALUCIA"
    url: https://www.diariodesevilla.es/
    max_to_fetch: 400
  
  - name: "MALAGA_HOY_ANDALUCIA"
    url: https://www.malagahoy.es/
    max_to_fetch: 400
  
  - name: "GRANADA_HOY_ANDALUCIA"
    url: https://www.granadahoy.com/
    max_to_fetch: 400
  
  - name: "HUELVA_INFORMACION_ANDALUCIA"
    url: https://www.huelvainformacion.es/
    max_to_fetch: 400
  
  - name: "EL_DIA_DE_CORDOBA_ANDALUCIA"
    url: https://www.eldiadecordoba.es/
    max_to_fetch: 400
  
  - name: "LAVOZ_DIGITAL_CADIZ_ANDALUCIA"
    url: https://www.lavozdigital.es/
    max_to_fetch: 400
  
  - name: "IDEAL_GRANADA_ANDALUCIA"
    url: https://www.ideal.es/
    max_to_fetch: 400
  
  # ARAGON
  - name: "HERALDO_DE_ARAGON_ARAGON"
    url: https://www.heraldo.es/
    max_to_fetch: 400
  
  - name: "EL_PERIODICO_DE_ARAGON_ARAGON"
    url: https://www.elperiodicodearagon.com/
    max_to_fetch: 400
  
  # ASTURIAS
  - name: "EL_COMERCIO_ASTURIAS"
    url: https://www.elcomercio.es/
    max_to_fetch: 400
  
  - name: "LA_NUEVA_ESPANA_ASTURIAS"
    url: https://www.lne.es/
    max_to_fetch: 400
  
  - name: "LA_VOZ_DE_ASTURIAS_ASTURIAS"
    url: https://www.lavozdeasturias.es/
    max_to_fetch: 400
  
  # BALEARES
  - name: "ULTIMA_HORA_BALEARES"
    url: https://www.ultimahora.es/
    max_to_fetch: 400
  
  - name: "DIARIO_DE_MALLORCA_BALEARES"
    url: https://www.diariodemallorca.es/
    max_to_fetch: 400
  
  # CANARIAS
  - name: "CANARIAS7_CANARIAS"
    url: https://www.canarias7.es/
    max_to_fetch: 400
  
  - name: "EL_DIA_CANARIAS"
    url: https://www.eldia.es/
    max_to_fetch: 400
  
  - name: "LA_PROVINCIA_CANARIAS"
    url: https://www.laprovincia.es/
    max_to_fetch: 400
  
  # CANTABRIA
  - name: "EL_DIARIO_MONTAÑES_CANTABRIA"
    url: https://www.eldiariomontanes.es/
    max_to_fetch: 400
  
  # CASTILLA_Y_LEON
  - name: "EL_NORTE_DE_CASTILLA_CYL"
    url: https://www.elnortedecastilla.es/
    max_to_fetch: 400
  
  - name: "DIARIO_DE_LEON_CYL"
    url: https://www.diariodeleon.es/
    max_to_fetch: 400
  
  - name: "BURGOS_CONECTA_CYL"
    url: https://www.burgosconecta.es/
    max_to_fetch: 400
  
  - name: "LA_GACETA_DE_SALAMANCA_CYL"
    url: https://www.lagacetadesalamanca.es/
    max_to_fetch: 400
  
  # CASTILLA_LA_MANCHA
  - name: "EN_CASTILLA_LA_MANCHA_CLM"
    url: https://www.encastillalamancha.es/
    max_to_fetch: 400
  
  - name: "LANZA_CIUDAD_REAL_CLM"
    url: https://www.lanza.es/
    max_to_fetch: 400
  
  - name: "DIARIO_LA_TRIBUNA_CLM"
    url: https://www.diariolatribuna.com/
    max_to_fetch: 400
  
  # CATALUNA (castellano y catalan)
  - name: "ARA_CATALUNA"
    url: https://www.ara.cat/
    max_to_fetch: 400
  
  - name: "NACIO_DIGITAL_CATALUNA"
    url: https://www.naciodigital.cat/
    max_to_fetch: 400
  
  - name: "EL_PUNT_AVUI_CATALUNA"
    url: https://www.elpuntavui.cat/
    max_to_fetch: 400
  
  - name: "DIARI_DE_GIRONA_CATALUNA"
    url: https://www.diaridegirona.cat/
    max_to_fetch: 400
  
  - name: "SEGRE_CATALUNA"
    url: https://www.segre.com/
    max_to_fetch: 400
  
  # COMUNIDAD_VALENCIANA
  - name: "LEVANTE_EMV_CV"
    url: https://www.levante-emv.com/
    max_to_fetch: 400
  
  - name: "INFORMACION_CV"
    url: https://www.informacion.es/
    max_to_fetch: 400
  
  - name: "LAS_PROVINCIAS_CV"
    url: https://www.lasprovincias.es/
    max_to_fetch: 400
  
  # EXTREMADURA
  - name: "HOY_EXTREMADURA"
    url: https://www.hoy.es/
    max_to_fetch: 400
  
  - name: "EL_PERIODICO_EXTREMADURA_EXTREMADURA"
    url: https://www.elperiodicoextremadura.com/
    max_to_fetch: 400
  
  # GALICIA
  - name: "LA_VOZ_DE_GALICIA_GALICIA"
    url: https://www.lavozdegalicia.es/
    max_to_fetch: 400
  
  - name: "FARO_DE_VIGO_GALICIA"
    url: https://www.farodevigo.es/
    max_to_fetch: 400
  
  - name: "EL_PROGRESO_GALICIA"
    url: https://www.elprogreso.es/
    max_to_fetch: 400
  
  - name: "LA_REGION_GALICIA"
    url: https://www.laregion.es/
    max_to_fetch: 400
  
  # MADRID
  - name: "MADRID_DIARIO_MADRID"
    url: https://www.madridiario.es/
    max_to_fetch: 400
  
  - name: "EL_BOLETIN_MADRID"
    url: https://www.elboletin.com/
    max_to_fetch: 400
  
  # MURCIA
  - name: "LA_VERDAD_MURCIA"
    url: https://www.laverdad.es/
    max_to_fetch: 400
  
  - name: "LA_OPINION_DE_MURCIA_MURCIA"
    url: https://www.laopiniondemurcia.es/
    max_to_fetch: 400
  
  - name: "MURCIA_DIARIO_MURCIA"
    url: https://murciadiario.com/
    max_to_fetch: 400
  
  # NAVARRA
  - name: "DIARIO_DE_NAVARRA_NAVARRA"
    url: https://www.diariodenavarra.es/
    max_to_fetch: 400
  
  - name: "NOTICIAS_DE_NAVARRA_NAVARRA"
    url: https://www.noticiasdenavarra.com/
    max_to_fetch: 400
  
  # PAIS_VASCO (castellano y euskera)
  - name: "EL_CORREO_PAIS_VASCO"
    url: https://www.elcorreo.com/
    max_to_fetch: 400
  
  - name: "DEIA_PAIS_VASCO"
    url: https://www.deia.eus/
    max_to_fetch: 400
  
  - name: "NOTICIAS_DE_GIPUZKOA_PAIS_VASCO"
    url: https://www.noticiasdegipuzkoa.eus/
    max_to_fetch: 400
  
  - name: "NOTICIAS_DE_ALAVA_PAIS_VASCO"
    url: https://www.noticiasdealava.eus/
    max_to_fetch: 400
  
  - name: "BERRIA_PAIS_VASCO"
    url: https://www.berria.eus/
    max_to_fetch: 400
  
  # LA_RIOJA
  - name: "LA_RIOJA_LA_RIOJA"
    url: https://www.larioja.com/
    max_to_fetch: 400
  
  # CEUTA_Y_MELILLA
  - name: "EL_FARO_DE_CEUTA_CEUTA"
    url: https://elfarodeceuta.es/
    max_to_fetch: 400
  
  - name: "EL_FARO_DE_MELILLA_MELILLA"
    url: https://elfarodemelilla.es/
    max_to_fetch: 400

Qué pueden cambiar:

keywords: una o varias palabras. Dejar vacío para sin filtro.

hours_recent: horas de ventana (p. ej., 24).

email.user y email.to_emails: remitente y destinatarios.

sources: añadir/quitar medios. Solo una url por medio.

2) Ejecutar o esperar a la automatización
Automático: el flujo corre con la frecuencia configurada (por defecto cada 5 minutos).

Manual: pestaña Actions → Noticias automáticas → Run workflow.

Primera vez: configurar el correo
En la cuenta Gmail del remitente, activar Verificación en dos pasos.

Crear App Password (16 caracteres) para “Correo”.

En GitHub: Settings → Secrets and variables → Actions → New repository secret

Name: SMTP_PASS

Value: la App Password (sin espacios).

El script usa SMTP_USER desde config.yaml y SMTP_PASS desde el Secret.

Frecuencia de ejecución
El workflow está en .github/workflows/noticias.yml.

Frecuencias comunes (editar cron):

Cada 5 minutos: */5 * * * *

Cada hora: 0 * * * *

Diario 06:00 UTC (~07:00 Madrid en invierno): 0 6 * * *

Guardar el cambio con Commit changes.

Ver logs y resolver problemas
Pestaña Actions → abrir la última ejecución → ver pasos y salida.

Errores típicos:

SMTPAuthenticationError 535: Secret SMTP_PASS incorrecto o revocado.

“0 artículos”: ampliar hours_recent, revisar keywords, o añadir más sources.

Cambios en la web: si una fuente cambia su HTML, avísanos para ajustar el parser.

Seguridad y control
La contraseña de Gmail no está en el código. Está en Secrets.

Todo queda versionado. Si algo falla tras editar config.yaml, usar History para revertir.
