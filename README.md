#Proyecto detector de placas
#Camilo Andres Espinoza Gualdron

###El primer paso para la creación del proyecto fue crear una instancia en AWS EC2 con la llave ya generada .pem y la ip publica que nos da el servidor, conectandonos desde cmd en la ubicacion donde tenemos la llave en nuestro equipo

####ssh -i "llave.pem" ubuntu@IP-PUBLICA

###Luego de la conexion instalamos las librerias necesarias para usar OpenCV y Python

####sudo apt-get update
####sudo apt-get install python3-pip python3-venv libgl1 -y

###Procedemos a crear el entorno virtual con los comandos 
####python3 -m venv entorno_ia
####source entorno_ia/bin/activate

###Instalamos las demas librerias YOLO, FastAPi
####pip install torch torchvision --index-url https://download.pytorch.org/whl/cpu --no-cache-dir
####pip install fastapi uvicorn ultralytics easyocr python-multipart opencv-python-headless pillow --no-cache-dir

###Subimos los archivos al servidor que sera el modelo entrenado best.pt y el app.py
####scp -i "tu-llave.pem" app.py ubuntu@TU-IP-PUBLICA:/home/ubuntu/
####scp -i "tu-llave.pem" best.pt ubuntu@TU-IP-PUBLICA:/home/ubuntu/
