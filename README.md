# Web Crawling SEO Analyzer

Ce projet présente quatre différentes méthodes de crawling pour extraire des informations SEO (titre, méta description, balises H1 et liens) à partir d'une URL donnée. Chaque méthode démontre une progression dans l'optimisation des performances et la gestion de la parallélisation.

## 1. Crawling séquentiel 

Dans cette première méthode, le crawling est effectué de manière **séquentielle**. Chaque URL est visitée une par une, et les informations SEO comme le titre, la description, les balises H1 ainsi que le nombre de liens sont extraites. Cette méthode est simple mais peut devenir inefficace lorsque le nombre de pages à analyser est élevé, car elle traite les URLs l’une après l’autre. 

## 2. Crawling multi-threadé_v1

Cette méthode introduit une **parallélisation** grâce au multi-threading. Plutôt que de crawler les pages séquentiellement, plusieurs pages sont explorées simultanément, ce qui permet de traiter plus rapidement des sites de taille moyenne à grande. Grâce à **`ThreadPoolExecutor`**, plusieurs requêtes HTTP sont envoyées en parallèle, accélérant le processus.

## 3. Crawling multi-threadé_v2

Dans cette méthode, la parallélisation est encore utilisée. En plus d'extraire les informations SEO, les nouveaux liens internes trouvés sur chaque page sont sauvegardés et ajoutés à une liste pour un crawling plus complet.

## 4. Crawling asynchrone 

La dernière méthode utilise toujours **`ThreadPoolExecutor`** un approche **asynchrone**, qui permet de traiter les pages dès que la réponse HTTP est reçue, sans attendre que les autres tâches se terminent. Cela permet un crawling beaucoup plus efficace, particulièrement pour les sites volumineux ou lents à répondre. L’utilisation d'outils comme **`as_completed`** permet d’optimiser encore davantage la gestion des requêtes, rendant cette méthode la plus rapide et la plus adaptée pour les grands sites.

---

## Conclusion

Ces quatre méthodes montrent ma progression dans l'optimisation des tâches de crawling, depuis un modèle séquentiel simple jusqu’à l’utilisation de multi-threading et d’asynchronisme.
