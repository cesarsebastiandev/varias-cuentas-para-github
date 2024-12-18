1.- INSTALAR GIT
2.- GENERAR LAS LLAVES PÚBLICAS Y PRIVADAS PARA CADA CORREO
ssh-keygen -t ed25519 -C "tu_primer_correo_electronico"
C:/Users/tu_usuario/.ssh/github-for-job
ssh-keygen -t ed25519 -C "tu_secundo_correo_electronico"
C:/Users/tu_usuario/.ssh/github-for-yt
3.- EN LA CARPETA SSH CREO UN ARCHIVO config SIN EXTENSIÓN.
4.- EN EL ARCHIVO config AGREGO EL SIGUIENTE CÓDIGO:

Host github-for-job
  Hostname github.com
  IdentityFile ~/.ssh/github-for-job
  IdentitiesOnly yes
  User git

Host github-for-yt
  Hostname github.com
  IdentityFile ~/.ssh/github-for-yt
  IdentitiesOnly yes
  User git
5.- AGREGO LAS CLAVES PÚBLICAS EN CADA REPOSITORIO
6.- CREO UN PROYECTO PARA CADA CUENTA DE GITHUB Y LO SUBO AL REPOSITORIO
Inicio el repositorio con git init
Agrego: git config user.email "cesarsebastian.dev@gmail.com"
Agrego los cambios hechos con: git add .
Hago un commit: git commit -m "My first GitHub account"
Agrego el repo de manera remota a mi proyecto con: git remote add origin git@tag_de_llave_ssh:nombre_de_usuario_en_github/nombre_del_repo.git
Subo cambios con: git push -u origin master O main

PARA CLONAR Y SUBIR CAMBIOS:
git clone git@tag_de_llave_ssh:nombre_de_usuario_en_github/nombre_del_repo.git


INFO EXTRA:
ssh -T git@tag_de_llave_ssh      ME DICE SI ESTOY AUTENTICADO CORRECTAMENTE

SI HABIAS CONFIGURADO UNA CUENTA DE FORMA GLOBAL ANTES Y AHORA QUIERES USAR VARIAS CUENTAS AL MISMO TIEMPO, DEBES EJECUTAR LOS SIGUIENTES COMANDOS PARA BORRAR LA INFO GLOBAL:
git config --global --unset user.name
git config --global --unset user.email