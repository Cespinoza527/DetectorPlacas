# Proyecto detector de placas
# Camilo Andres Espinoza Gualdron

## El primer paso para la creación del proyecto fue crear una instancia en AWS EC2 con la llave ya generada .pem y la ip publica que nos da el servidor, conectandonos desde cmd en la ubicacion donde tenemos la llave en nuestro equipo

#### ssh -i "llave.pem" ubuntu@IP-PUBLICA

## Luego de la conexion instalamos las librerias necesarias para usar OpenCV y Python

#### sudo apt-get update
#### sudo apt-get install python3-pip python3-venv libgl1 -y

## Procedemos a crear el entorno virtual con los comandos 
#### python3 -m venv entorno_ia
#### source entorno_ia/bin/activate

## Instalamos las demas librerias YOLO, FastAPi
#### pip install torch torchvision --index-url https://download.pytorch.org/whl/cpu --no-cache-dir
#### pip install fastapi uvicorn ultralytics easyocr python-multipart opencv-python-headless pillow --no-cache-dir

## Subimos los archivos al servidor que sera el modelo entrenado best.pt y el app.py
#### scp -i "tu-llave.pem" app.py ubuntu@TU-IP-PUBLICA:/home/ubuntu/
#### scp -i "tu-llave.pem" best.pt ubuntu@TU-IP-PUBLICA:/home/ubuntu/

###Ejecutamos el servidor 
#### python3 app.py

#Creación de APP Expo GO
## Creamos la carpeta del proyecto con Expo Go como un template vacio
#### npx create-expo-app DetectorPlacas --template expo-template-blank-typescript
#### cd DetectorPlacas

## Instalamos las dependencias necesarias para el proyecto
#### npx expo install expo-camera expo-speech expo-image-manipulator expo-router expo-splash-screen expo-build-properties axios react-native-safe-area-context react-native-screens expo-constants expo-linking

## Configuramos el proyecto como permisos de camara microfono en app.json tambien cambiamos la logica del index.tsx por el archivo encontrado en la carpeta https://github.com/adiacla/Deployment-Mobile-Yolo

## Generamos el apk del proyecto mediante los comandos

#### npm install -g eas-cli
#### eas login
#### eas build:configure
#### eas build -p android --profile preview

<img width="1916" height="826" alt="image" src="https://github.com/user-attachments/assets/d46ce99b-a126-4789-8160-7784d8445b16" />
