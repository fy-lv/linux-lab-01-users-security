# Linux Lab 01 – Users & Security

## Objetivo
Configurar un sistema Linux para un entorno multiusuario aplicando buenas prácticas:
- usuarios y grupos
- políticas de contraseña / expiración
- sudo restringido (mínimo privilegio)
- configuración por defecto con /etc/skel

## Entorno / prerequisitos
- Linux (indicar distro y versión)
- Acceso root o usuario con sudo
- Recomendado: VM con snapshot antes de empezar

## Escenario
Servidor Linux sin políticas de usuarios, grupos ni control de privilegios. :contentReference[oaicite:5]{index=5}

## Pasos

### 1) Crear grupos y usuarios
**Comandos**
```bash
# ejemplos (ajustar a tu caso)
sudo groupadd secops
sudo useradd -m -s /bin/bash user1
sudo usermod -aG secops user1

getent group secops
id user1

# ejemplo:
sudo chage -M 90 -m 7 -W 14 user1

chage -l user1

sudo visudo -f /etc/sudoers.d/user1-lab01
# ejemplo dentro:
# user1 ALL=(ALL) NOPASSWD: /usr/bin/systemctl status, /usr/bin/journalctl

sudo -l -U user1

# ejemplo:
sudo ls -la /etc/skel
# agregar .bashrc, aliases, etc...

# crear user2 y verificar que hereda
sudo useradd -m -s /bin/bash user2
sudo -u user2 ls -la ~
