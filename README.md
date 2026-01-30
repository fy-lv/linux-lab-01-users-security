# Linux Lab 01 – Users & Security

## 📌 Objetivo
Configurar un sistema Linux básico para entorno multiusuario aplicando buenas prácticas de seguridad: gestión de usuarios, grupos, contraseñas y sudo. :contentReference[oaicite:1]{index=1}

---

## 🧩 Escenario
Un servidor Linux sin políticas definidas de usuarios, grupos ni control de privilegios. :contentReference[oaicite:2]{index=2}

---

## 📋 Alcance del laboratorio
- Crear usuarios y grupos.
- Configurar políticas de contraseñas.
- Restringir uso de `sudo`.
- Usar `/etc/skel` para configuración por defecto. :contentReference[oaicite:3]{index=3}

---

## 🛠️ Comandos utilizados

> Lista completa en el archivo **commands**

Ejemplos:
```bash
# Crear grupo
sudo groupadd developers

# Añadir usuario con grupo principal
sudo useradd -m -G developers username

# Revisar usuario y grupo
getent passwd
getent group

sudo chage -l username
sudo chage -m 1 -M 90 -W 7 username

sudo visudo
# permitir solo comandos específicos por usuario/grupo

