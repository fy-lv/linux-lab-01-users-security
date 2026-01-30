# Linux Lab 01 – Users & Security

## Objetivo
Configurar un sistema Linux básico para entorno multiusuario aplicando buenas prácticas de seguridad.

## Escenario
Servidor Linux sin políticas de usuarios, grupos ni control de privilegios.

## Alcance
- Usuarios y grupos
- Políticas de contraseñas
- sudo restringido
- Configuración por defecto con /etc/skel

## Verificación
- getent group
- getent passwd
- id
- chage -l
- sudo -l
