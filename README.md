# SOAP

Ce projet a pour objectif de mettre en place un service web SOAP en Java en utilisant la technologie JAX-WS. Le service est exécuté en local et permet à des clients d’invoquer différentes méthodes à distance grâce au protocole SOAP. L’idée principale est de comprendre le fonctionnement des services web et la communication entre un client et un serveur via des échanges XML.

Pour réaliser ce projet, plusieurs technologies ont été utilisées. Le développement repose sur Java SE, avec l’utilisation du protocole SOAP pour les échanges. L’API JAX-WS permet de créer et d’exposer le service web, tandis que JAXB est utilisé pour la sérialisation et la conversion des objets Java en XML. La communication se fait via le protocole HTTP.

L’architecture du projet s’appuie sur trois classes principales. La classe Application a pour rôle de démarrer le programme et de publier le service web afin qu’il soit accessible aux clients. La classe MonserviceWeb contient les différentes méthodes mises à disposition à distance. Enfin, la classe Etudiant représente l’objet métier utilisé pour échanger des données entre le client et le service.

La classe Application permet de lancer le serveur et de rendre le service disponible à l’adresse locale http://localhost:8888/
. Grâce à la méthode Endpoint.publish(), le service devient accessible et peut être interrogé par un client SOAP.

La classe MonserviceWeb constitue le cœur du service. Elle est annotée avec l’annotation @WebService, ce qui permet d’exposer ses méthodes. Parmi les fonctionnalités proposées, on retrouve une méthode de conversion appliquée à un montant, une méthode permettant d’effectuer la somme de deux nombres, ainsi qu’une méthode retournant un objet Etudiant à partir d’un identifiant.

La classe Etudiant modélise les informations relatives à un étudiant. Elle contient notamment un identifiant, un nom et une moyenne. Cette classe est compatible avec JAXB, ce qui permet sa transformation automatique en XML lors des échanges entre le client et le serveur.

Le fonctionnement global du service repose sur plusieurs étapes. Tout d’abord, l’application est lancée et le service est déployé. Ensuite, un client envoie une requête SOAP au serveur. La méthode correspondante est exécutée côté serveur, puis une réponse est renvoyée sous forme de message XML.

Enfin, le service génère automatiquement un WSDL accessible à l’adresse http://localhost:8888/?wsdl
. Ce fichier décrit l’ensemble des méthodes disponibles ainsi que les types de données utilisés. Ce projet illustre ainsi une implémentation simple mais complète d’un service web SOAP en Java et permet de comprendre les bases du fonctionnement de JAX-WS et des échanges SOAP.
