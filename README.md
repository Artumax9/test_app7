The course of rails developer 

# Crear el directorio .ssh en WSL si no existe
mkdir -p ~/.ssh

# Copiar la clave privada desde el sistema de archivos de Windows a WSL
cp /mnt/c/Users/artur/.ssh/id_ed25519 ~/.ssh/

# Ajustar los permisos de la clave privada copiada
chmod 600 ~/.ssh/id_ed25519

# Añadir la clave SSH al agente desde la ubicación WSL
ssh-add ~/.ssh/id_ed25519

# Verificar la conexión con GitHub
ssh -T git@github.com

# Hacer push de nuevo
git push -u origin main
