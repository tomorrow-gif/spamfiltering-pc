# Spam filtering (filtrado de información no deseada)

> 🌍 [简体中文](README.zh-CN.md) · [繁體中文](README.zh-TW.md) · [English](README.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Deutsch](README.de.md) · [Français](README.fr.md) · [Español](README.es.md) · [Português](README.pt.md) · [Русский](README.ru.md)

Mantenga limpia su navegación. **Spam filtering** elimina automáticamente spam, ventanas emergentes, banners, rastreadores y otro contenido no deseado de las páginas que visita; todo se ejecuta localmente y de forma privada en su dispositivo.

## Características

- Bloquea spam y contenido no deseado: ventanas emergentes, banners, rastreadores, scripts de análisis
- Sus propias reglas en texto plano: importe, edite y exporte cuando quiera
- Lista blanca de sitios de confianza con un clic
- Estadísticas de bloqueo (hoy / total)
- Compatible con 10 idiomas
- 100 % local y privado: sin cuentas, sin nube, sin recopilación de datos
- Funciona a nivel de sistema: no requiere extensión de navegador

## Requisitos

- Windows 10 / 11

## Primeros pasos

1. Descargue el instalador más reciente desde la página de Releases.
2. Instale e inicie la aplicación.
3. Active **Tomar el control del proxy del sistema** en Configuración.
4. Navegue con normalidad: el contenido no deseado se filtra automáticamente.

## Edición de reglas

Las reglas se almacenan en texto plano, una regla por línea. Añada reglas en la página **Reglas** de la aplicación o importe un archivo de reglas.

### Formatos de regla

| Ejemplo | Significado |
| --- | --- |
| `\|\|example.com^` | Bloquear un dominio y todos sus subdominios |
| `\|\|example.com/path/page^` | Bloquear una dirección específica (dominio + ruta) |
| `example.com` | Bloquear cualquier dirección que contenga este texto |
| `@@\|\|good.example.com^` | Excepción: permitir siempre este dominio |
| `0.0.0.0 ad.example.com` | Entrada en formato hosts |
| `! comentario` / `# comentario` | Líneas de comentario: las líneas que empiezan con estos caracteres se ignoran |

### Consejos

- `||` ancla la regla al inicio del dominio; `^` significa «fin del dominio o de la ruta» (un separador).
- Empiece simple: `||dominio^` cubre la mayoría de los casos. Añada reglas de ruta solo si es necesario, p. ej. `||www.example.com/ads/banner^`.
- Tras guardar una regla, revise las estadísticas de bloqueo para confirmar que funciona.

### Acerca de HTTPS

Por defecto, las solicitudes HTTPS se comparan solo por **nombre de dominio** (la dirección completa está cifrada y no puede verse). Para comparar por **dirección completa, incluida la ruta**, active **Descifrado HTTPS (MITM)** en Configuración, instale el certificado raíz cuando se le pida (una sola vez) y reinicie su navegador. Después, reglas de ruta como `||www.example.com/ads/banner^` también funcionan en sitios HTTPS.

## Cómo funciona (breve)

- La aplicación ejecuta un proxy local y puede tomar el control del proxy del sistema, de modo que el tráfico del navegador pasa por él.
- Cada solicitud se compara con sus reglas: las coincidencias se bloquean, todo lo demás se reenvía sin cambios.
- Todo el filtrado ocurre en su dispositivo: no se sube nada a ningún sitio.

## Solución de problemas

**¿No puede acceder a Internet?** La causa más probable: la aplicación se cerró inesperadamente y dejó el proxy del sistema apuntando a un puerto no válido.

- **Solución 1: reinicie la aplicación.** Detecta y limpia automáticamente los ajustes de proxy residuales al iniciarse.
- **Solución 2: desactive el proxy manualmente.** Configuración de Windows → Red e Internet → Proxy → desactive «Usar un servidor proxy».
- Normalmente, al salir de la aplicación (icono de la bandeja → Salir) el proxy se restaura automáticamente. Los restos solo ocurren tras salidas anormales (bloqueo, cierre forzado, corte de energía).

## Privacidad

Spam filtering es una herramienta local. Todo el filtrado se realiza en su dispositivo: sus datos de navegación nunca salen de su ordenador.

## Apoyar este proyecto

Si Spam filtering le resulta útil, considere apoyar el desarrollo futuro:

![Donate](donate.jpg)

## Licencia

Todos los derechos reservados. Este software **no es de código abierto**. No se permite la redistribución ni la modificación sin autorización escrita explícita.
