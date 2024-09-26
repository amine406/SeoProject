# Web Crawling SEO Analyzer

Ce projet présente quatre différentes méthodes de crawling pour extraire des informations SEO (titre, méta description, balises H1 et liens) à partir d'une URL donnée. Chaque méthode démontre une progression dans l'optimisation des performances et la gestion de la parallélisation, illustrant ma compréhension des techniques de crawling et des bonnes pratiques de développement.

## 1. Crawling séquentiel simple

Dans cette première méthode, le crawling est effectué de manière **séquentielle**. Chaque URL est visitée une par une, et les informations SEO comme le titre, la description, les balises H1 ainsi que le nombre de liens sont extraites. Cette méthode est simple mais peut devenir inefficace lorsque le nombre de pages à analyser est élevé, car elle traite les URLs l’une après l’autre. Elle est adaptée pour des sites de petite taille où la performance n'est pas une contrainte majeure.

## 2. Crawling multi-threadé basique

Cette méthode introduit une **parallélisation** grâce au multi-threading. Plutôt que de crawler les pages séquentiellement, plusieurs pages sont explorées simultanément, ce qui permet de traiter plus rapidement des sites de taille moyenne à grande. Grâce à `ThreadPoolExecutor`, plusieurs requêtes HTTP sont envoyées en parallèle, accélérant considérablement le processus. Cependant, la synchronisation entre les threads peut nécessiter une attention particulière, surtout sur des sites très volumineux.

## 3. Crawling multi-threadé avec export avancé

Dans cette méthode, la parallélisation est encore utilisée, mais avec une gestion plus sophistiquée des données. En plus d'extraire les informations SEO, les nouveaux liens internes trouvés sur chaque page sont sauvegardés et ajoutés à une liste pour un crawling plus complet. Cela permet d’avoir une meilleure couverture du site en analysant ses liens internes de manière plus approfondie. Cette approche est également utile pour générer un aperçu structuré des pages visitées et des liens détectés. Les données sont ensuite exportées dans un fichier CSV.

## 4. Crawling asynchrone optimisé

La dernière méthode adopte une approche **asynchrone**, qui permet de traiter les pages dès que la réponse HTTP est reçue, sans attendre que les autres tâches se terminent. Cela permet un crawling beaucoup plus efficace, particulièrement pour les sites volumineux ou lents à répondre. L’utilisation d'outils comme `as_completed` permet d’optimiser encore davantage la gestion des requêtes, rendant cette méthode la plus rapide et la plus adaptée pour les grands sites. L’asynchronisme ajoute une complexité supplémentaire dans la gestion des erreurs et des exceptions, mais offre des performances optimales.

---

## Conclusion

Ces quatre méthodes montrent ma progression dans l'optimisation des tâches de crawling, depuis un modèle séquentiel simple jusqu’à l’utilisation de techniques avancées de multi-threading et d’asynchronisme. Ce projet démontre ma capacité à adapter mes solutions en fonction des besoins de performance et de gestion de données, tout en appliquant des bonnes pratiques dans le développement d’applications scalables.
