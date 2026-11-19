Projet 37 — Commerce agricole Maroc–Afrique (HS07 et HS08)
Binôme : Nom Prénom 1 / Nom Prénom 2 — ENCG Casablanca, Commerce International
Description
Analyse en panel et prévision à un an des exportations marocaines de légumes (HS07) et de fruits (HS08) vers 15 partenaires africains (2010–2024), à partir de l'API publique UN Comtrade. Trois approches comparées sans fuite temporelle : persistance, Ridge, forêt aléatoire.
Contenu
Projet37_Maroc_Afrique.ipynb : notebook exécutable de bout en bout.
rapport_projet37.tex / rapport_projet37.pdf : rapport scientifique.
soutenance_projet37.tex / soutenance_projet37.pdf : support de présentation.
notes_soutenance.md : notes pour l'oral.
figures/ : neuf figures PNG produites par le notebook.
data/ : données brutes reçues de l'API, panel nettoyé, tableau comparatif, journal des requêtes, paramètres de reproductibilité.
requirements.txt : dépendances.
Exécution
pip install -r requirements.txt (inutile sur Google Colab).
Ouvrir le notebook et lancer Exécution > Tout exécuter. Graine aléatoire : 42.
Si data/comtrade_maroc_exports_brut.csv est présent dans livrables/data/, le notebook le relit au lieu de rappeler l'API (résultats identiques). Sinon il interroge l'API (environ une minute).
Source
UN Comtrade — https://comtradeapi.un.org/public/v1/preview/C/A/HS — documentation : https://uncomtrade.org/docs/un-comtrade-api/. Extraction du 19/11/2026. Point d'accès public limité à 500 lignes par requête.
Résultats principaux (jeu de test, cibles 2023–2024)
             MAE validation  MAE test  RMSE test  WAPE test (%)
Persistance               0.730     0.809      1.596         30.520 Ridge                     0.767     1.165      2.400         43.921 Forêt aléatoire           0.966     0.896      1.560         33.807
