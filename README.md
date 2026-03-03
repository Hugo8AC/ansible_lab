# ansible_lab
Laboratorio para creacion de playbooks 

# Carpeta inventario
	Aqui es donde se guarda el directorio telefonico de los servidores 
	Dentro se tiene el archivo hosts.ini
	Contenido: Solo debe listar las IPs o nombres de los servidores bajo grupos.
	Ejemplo 
	[windows]
172.16.93.128

# Carpeta group_vars/
Esta es la "caja fuerte" y de configuración de Ansible.
Qué hacer: Crea un archivo llamado exactamente igual que el grupo en tu inventario (en este caso, windows.yml).
Contenido: Aquí pones los parámetros de conexión para que no ensucien tu inventario.

# Carpeta playbooks/
Aquí guardas los "manuales de instrucciones".
Qué hacer: Mueve aquí tu archivo setup_iis.yml (y todos los .yml que crees en el futuro).
Beneficio: Mantienes la raíz de tu proyecto limpia. Cuando tengas 10 playbooks diferentes (uno para Chrome, otro para parches de seguridad), agradecerás tenerlos ordenados aquí.

# Archivo ansible.cfg (En la raíz)
Este es el "cerebro" que coordina todo.
Qué hacer: Configúralo para que no tengas que escribir rutas largas en la terminal.
[defaults]
inventory = ./inventories/hosts.ini  # Le dice dónde están los servidores
host_key_checking = False             # Evita errores de certificados