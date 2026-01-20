## Política de contraseñas (usuarios existentes)
chage -M 60 -W 7 alice
chage -M 60 -W 7 bob
chage -M 60 -W 7 carol
chage -M 60 -W 7 dave

## Configuración por defecto
grep -E 'PASS_MAX_DAYS|PASS_WARN_AGE' /etc/login.defs
