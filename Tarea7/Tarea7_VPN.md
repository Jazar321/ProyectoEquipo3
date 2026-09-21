# Guía de configuración de VPN en Windows

Esta guía, dirigida a colaboradores con equipos con Sistema  Windows 10 u 11 que  tienen la necesidad de  acceder a recursos internos (carpetas compartidas, intranet, sistemas internos) desde fuera de la oficina, explica cómo configurar una conexión VPN empresarial en Windows para acceder de forma segura a los recursos internos de la organización.

# Síntomas

-No es posible abrir carpetas compartidas, la intranet o sistemas internos desde casa o una red externa.
-Aparece el mensaje “No se puede conectar a [nombre de la VPN]” o errores como 691, 800 o 809.
-La conexión VPN no aparece en la lista de redes del equipo.

# Causa probable

La conexión VPN no está configurada en el equipo, se configuró con datos incorrectos (servidor, tipo de VPN o clave precompartida), o las credenciales de dominio están vencidas o mal escritas.

## Requisitos

Antes de comenzar, asegúrese de contar con:

* Conexión estable a Internet.
* Usuario y contraseña de dominio activos.
* Clave precompartida proporcionada por Mesa de Ayuda.
* MFA habilitado, si aplica.

## Configuración

1. Verifique la conexión a Internet accediendo a cualquier página web.
2. Vaya a **Inicio > Configuración > Red e Internet > VPN** y seleccione **Agregar VPN**.
3. Configure los campos:

   * **Proveedor de VPN:** Windows (integrado)
   * **Nombre de conexión:** VPN Empresa
   * **Servidor:** `vpn.empresa.com`
   * **Tipo de VPN:** L2TP/IPsec con clave precompartida
   * **Clave precompartida:** proporcionada por Mesa de Ayuda
4. En **Tipo de información de inicio de sesión**, seleccione **Nombre de usuario y contraseña**.
5. Introduzca el usuario en formato `EMPRESA\usuario` y la contraseña de dominio. Seleccione **Guardar**.
6. Seleccione **VPN Empresa** y haga clic en **Conectar**.
7. Si se solicita MFA, apruebe el inicio de sesión en la aplicación de autenticación.

## Validación

La conexión es correcta cuando:

* **VPN Empresa** aparece como **Conectado**.
* Puede acceder a la intranet o a una carpeta compartida.
* El comando `ping servidor01.empresa.local` devuelve respuestas.

## Solución de problemas

* **Error 691:** revise el usuario, la contraseña y el formato de dominio.
* **Error 800:** compruebe la conexión a Internet o pruebe otra red.
* **Error 809:** pruebe desde una red diferente.

Si el problema persiste, contacte a **Mesa de Ayuda** en **[mesadeayuda@empresa.com](mailto:mesadeayuda@empresa.com)** e incluya:

* Nombre y usuario.
* Número de equipo o etiqueta de inventario.
* Código o captura del error.
* Tipo de red utilizada.
* Hora aproximada del intento.

**Escalamiento:** N1 → N2 Redes.

## NOTA DE SEGURIDAD
Nunca comparta su contraseña ni la clave precompartida, y desconecte la VPN al terminar de trabajar, especialmente en redes públicas.