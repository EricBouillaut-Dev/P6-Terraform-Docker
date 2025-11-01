# Projet 6 : Infrastructure as Code avec Terraform et Docker

Ce projet implémente une Infrastructure as Code (IaC) avec Terraform pour déployer un conteneur Nginx sur Docker.

## Description

Ce projet déploie automatiquement un conteneur Nginx en utilisant Terraform. Le conteneur expose le port 80 interne sur le port 8080 de la machine hôte.

## Prérequis

- Terraform installé (v1.9.0 ou supérieur)
- Docker installé et en cours d'exécution
- Accès à Internet pour télécharger l'image Docker

## Structure du projet

```
.
├── main.tf           # Configuration Terraform principale
├── .gitignore        # Fichiers à exclure du versionnement
└── README.md         # Documentation du projet
```

## Configuration

Le fichier `main.tf` contient :
- Un provider Docker configuré
- Une ressource `docker_image` utilisant l'image `nginx:latest`
- Une ressource `docker_container` créant un conteneur Nginx avec mapping de port 80->8080

## Déploiement

1. Initialiser Terraform :
   ```bash
   terraform init
   ```

2. Visualiser le plan d'exécution :
   ```bash
   terraform plan
   ```

3. Appliquer la configuration :
   ```bash
   terraform apply
   ```

## Vérification

Après le déploiement, vous pouvez vérifier que le conteneur fonctionne :

```bash
# Lister les conteneurs en cours d'exécution
docker ps

# Vérifier l'état de l'infrastructure
terraform show

# Tester l'accès à Nginx
curl http://localhost:8080
```

## Détails techniques

- **Image Docker** : nginx:latest
- **Port interne** : 80
- **Port externe** : 8080
- **Nom du conteneur** : nginx-container

## Nettoyage

Pour supprimer les ressources créées :

```bash
terraform destroy
```

## Auteur

Nom : Eric Bouillaut
Contexte : Projet réalisé dans le cadre de la formation OC-Expert DevOps - Projet 6

