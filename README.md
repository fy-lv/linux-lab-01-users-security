# Linux Lab 01 – Users & Security

Laboratorio práctico para configurar un sistema Linux básico en un entorno multiusuario aplicando buenas prácticas de seguridad:
usuarios/grupos, políticas de contraseña, sudo restringido y defaults con `/etc/skel`.  

---

## Objetivo

Configurar un sistema Linux para un entorno multiusuario aplicando:
- **Usuarios y grupos**
- **Políticas de contraseñas / expiración**
- **Sudo restringido (mínimo privilegio)**
- **Configuración por defecto para nuevos usuarios con `/etc/skel`** 
---

## Escenario

Servidor Linux sin políticas de usuarios, grupos ni control de privilegios. 

---

## Prerequisitos

- Linux (Debian/Ubuntu/RHEL-like). Recomendado en VM con snapshot.
- Acceso `root` o un usuario con `sudo`.
- Paquetes típicos ya instalados (coreutils, passwd/shadow utils, sudo).

> Nota: este lab **modifica usuarios/grupos y sudoers**. Hazlo en un entorno de laboratorio.

---

## Convenciones del lab (para que sea reproducible)

Este lab usa valores **consistentes**. Si cambias algo, cámbialo también en `commands/` y en el README.

### Usuarios / grupos usados
- Grupo: `secops`
- Usuarios: `user1`, `user2`

### Política de expiración (ejemplo recomendado)
- Expiración máxima: **90 días**
- Mínimo: **7 días**
- Warning: **14 días**

### Sudo restringido (ejemplo recomendado)
- El grupo `secops` podrá ejecutar **solo**:
  - `systemctl status`
  - `journalctl`
- Sin acceso a “ALL” ni a shells.

---

## Estructura del repositorio

- `commands/` → scripts del lab (ejecución)
- `evidence/` → outputs reales de verificación (prueba)
- `README.md` → guía (explicación) 

---

## Ejecución

### Opción A — Ejecutar todo (recomendado)
```bash
cd commands
sudo bash 00_run_all.sh
