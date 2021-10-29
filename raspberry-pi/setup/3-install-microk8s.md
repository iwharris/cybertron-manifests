```bash
sudo apt update && sudo apt upgrade -y

sudo snap install microk8s --classic

sudo usermod -a -G microk8s ubuntu
sudo chown -f -R ubuntu ~/.kube
newgrp microk8s
```