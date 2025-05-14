# Lancer le projet Symfony avec Docker

Ce projet utilise Docker pour simplifier le lancement. Voici comment le faire :

## Instructions

1.  **Clone le projet :**

    ```bash
    git clone git@github.com:ThomasDev6/symfony_docker.git
    cd symfony_docker
    ```

2.  **Configure l'environnement :**

    * Crée un fichier `.env` à la racine du projet et ajoute ces lignes (ou modifie-les si nécessaire) :

        ```
        APP_ENV=dev
        APP_SECRET=CHANGE_MOI_PAR_UNE_VALEUR_SECURISEE
        DATABASE_URL="postgresql://root:root@database:5432/db?serverVersion=13&charset=utf8"
        ```

        * **Important :** Remplace `CHANGE_MOI_PAR_UNE_VALEUR_SECURISEE` par une chaîne de caractères aléatoire et complexe.

3.  **Lance les conteneurs :**

    ```bash
    task start
    ```

4.  **C'est tout !** Ton application est maintenant accessible à l'adresse `http://localhost:8080`.

## Commandes Docker utiles

* **Stopper le projet :**

    ```bash
    task stop
    ```

* **Relancer le projet (après modifications, par exemple) :**

    ```bash
    task restart
    ```

* **Exécuter une commande Symfony :**

    ```bash
    task symfony [commande]
    ```

    * Exemple : `task symfony doctrine:migrations:migrate`