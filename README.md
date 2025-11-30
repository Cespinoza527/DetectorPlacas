El primer paso para la creación del proyecto fue crear una instancia en AWS EC2 con la llave ya generada .pem y la ip publica que nos da el servidor, conectandonos desde cmd en la ubicacion donde tenemos la llave en nuestro equipo

ssh -i "llave.pem" ubuntu@IP-PUBLICA

Luego de la conexion instalamos las librerias necesarias para usar OpenCV y Python

sudo apt-get update
sudo apt-get install python3-pip python3-venv libgl1 -y

Y procedemos a crear el entorno virtual con los comandos 
python3 -m venv entorno_ia
source entorno_ia/bin/activate

