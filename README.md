# Tema Horizon del Cloud OpenStack del STIC (Universidad de Almería)

## 

1. Descargar tema y compilar el tema

```bash
cd /usr/share/openstack-dashboard/openstack_dashboard/themes/
git clone https://github.com/ualmtorres/ost

cd /usr/share/openstack-dashboard
python3 manage.py collectstatic
python3 manage.py compress
```

2. Añadir el nuevo tema al archivo de configuración de Horizon

Editar el archivo `/etc/openstack-dashboard/local_settings.py` y hacer los cambios siguientes. Los cambios añaden el tema a la lista de temas disponibles y deja este tema como tema predeterminado.

```
....
AVAILABLE_THEMES = [
    ('default', 'Default', 'themes/default'),
    ('material', 'Material', 'themes/material'),
    ('example', 'Example', 'themes/example'),
    ('ost', 'STIC', 'themes/ost'),
]
....
DEFAULT_THEME = 'ost'
...
```

3. Reiniciar Apache

```
service apache2 restart
```


[OpenStack Horizon](https://github.com/openstack/horizon).
