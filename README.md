# Rapport-TP2-Traitement-de-signal
 Réalisé par :Fatima Ezzahraa Chadni

 # Thème :Traitement du signal ECG.
 
 # Objectifs:
   -Suppression du bruit autour du signal produit par un électrocardiographe.
   - Recherche de la fréquence cardiaque.
   
-Travail Demandé: Réaliser un script Matlab commenté qui contient le travail réalisé avec les représentations graphique expliquées sur le travail Effectué.

# Manipulation 1: Suppression du bruit provoqué par les mouvements du corps.
  Premièrement,on commence par charger le fichier ‘bluewhale.au’,qui contient le sous-ensemble de données qui 
  correspond au chant du rorqual bleu du Pacifique.Pour cela , on utilise la comande load comme représenté dans le script ci-dessous.
  
  ![image](https://user-images.githubusercontent.com/120644217/213816835-106cdf3d-b758-4290-b05f-f56eb39e5f65.png)
  
  On définit ensuite l'intervalle de temps au niveau duquel on va travailler ainsi que la période d'échantillonage Te et la fréquence associée Fe.Ensuite, on représente   le signal dans le domaine temporel.
  
  ![image](https://user-images.githubusercontent.com/120644217/213817158-42d62e68-a09f-488c-bccc-da985858b116.png)

  # Application de la Transformée de Fourrier au Signal ECG
  On commence par déterminer l'intervalle de fréquence fshift afin de centrer notre spectre fréquentiel autour de l'axe des ordonnées et normaliser les valeurs.
  Pour cette opération,on s'appuie aussi sur la commande fftshift comme mentionné dans le script.
  
  ![image](https://user-images.githubusercontent.com/120644217/213817871-eba9997c-489f-4a2d-9d3f-0d46e1a3c645.png)
  
  # Représentation du spectre fréquentiel .
  
  ![image](https://user-images.githubusercontent.com/120644217/213818058-ccf1b822-66d5-41fa-8fc8-a8da06559ef1.png)

  On observe dans la figure ci-dessous 3 pics de fréquence comme mentionné dans la figure ci-dessous.Ceci correspond au fréquences que contient le son du rorqual bleu.
  # Suppression du bruit à basse fréquence du signal ECG à travers l'opération de Filtrage.
  A ce stade,on commence par filtrer notre signal, et commence par l'élimination des basses fréquences (exactement les fréquences inférieures à 0.5 Hz.
  On utilise un filtre passe-haut pour effectuer ce filtrage.
  La fréquence de coupure utilisée pour ce filtre est de fc=0.5 Hz.
  Après la conception de notre filtre, on l'applique à notre signal dans domaine fréquentiel.
  Afin de représenter le signal dans le domaine temporel après filtrage,on utilise la commande ifft comme représenté dans le script ci-dessous.
  
  ![image](https://user-images.githubusercontent.com/120644217/213820232-2a1212a4-93c9-49c3-a60c-6404c1fa3e75.png)
  #  Représentation du signal ECG dans le domaine temporel après filtrage des basses fréquences.
   Une remarque importante sur le signal ECG après filtrage est que le signal est devenu plus régulier qu'auparavant et un signal sous forme d'une sinusoide est            supprimé.
  
  ![image](https://user-images.githubusercontent.com/120644217/213820475-e5bd893d-5e55-4333-983d-414744ebab4f.png)
  # Représentation fréquentielle.
  ![image](https://user-images.githubusercontent.com/120644217/213820593-657ec48a-3e4a-44b7-85d0-2400fb8eb557.png)
  
  # Suppression des interférences des lignes électriques 50Hz.
  Pour effectuer cette opération,on se sert d'un filtre de type Notch pour éliminer une valeur de fréquence bien définie au lieu d'une bande de fréquence bien           déterminée.
  
  ![image](https://user-images.githubusercontent.com/120644217/213821501-007311ec-a7ee-4607-8905-f4d90cb9cde6.png)
  
  La figure représentée ci-dessous illustre en premier temps le signal ECG initial,puis sa représentation après les deux filtres effectués.
  Ensuite,la représentation du bruit devient utile pour observer bien le bruit éliminé de notre signal .
  
  ![image](https://user-images.githubusercontent.com/120644217/213821838-2d88400d-0aca-48e2-ab55-7f6546cb64f9.png)
  
  #  Amélioration du rapport signal sur bruit.
  Pour réaliser cette opération,on effectue un test à travers différentes valeurs de fréquence de coupure.Pour notre cas,on utilise une fréquence de coupure dont la 
   valeur est de 37 Hz.
   
   ![image](https://user-images.githubusercontent.com/120644217/213822496-07163c4f-d63a-4126-a7d4-d4ebf31673d0.png)
   
   Après réalisation de filtrage suivant la valeur de fréquence déterminée ,on obtient l'amélioration suivante du signal représentée par la figure ci-dessous.
   
   ![image](https://user-images.githubusercontent.com/120644217/213822726-220fa906-1e49-4bfb-afe5-a3ae1a43bee4.png)
   
   # Identification de la fréquence cardiaque grace à la fréquence d'autocorrélation.
   On calcule la fonction d'autocorrélation à travers le code suivant .Pour ce cas illustré,
   on utilise le signal ECG3 comme signal de base pour calculer sa fonction 
   d'autocorrélation.
     
![image](https://user-images.githubusercontent.com/120644217/213824027-acc9c9ef-c6c6-4a5c-b550-c3ea9967bed4.png)

 La représentation de cette fonction est visualisée comme suit:
 
 ![image](https://user-images.githubusercontent.com/120644217/213824237-abaa1b34-d969-4f8e-b609-1826103811d0.png)

     

   
 

   

  
