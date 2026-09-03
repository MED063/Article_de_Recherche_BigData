# Article de Recherche — Big Data

Rendu de groupe sur l'article **"Carbon Accounting and Beyond: An Evidence-Based Life Cycle Assessment of the Environmental Impacts of Data Center IT Equipment"**, Smith, M., Mann, M. & Lal, P. (2026), *Sustainability*, 18(11), 5671. [doi.org/10.3390/su18115671](https://doi.org/10.3390/su18115671)

L'étude compare trois méthodes de comptabilité carbone (ACV/LCA, average-data, spend-based) appliquées aux équipements IT d'un data center, et teste deux scénarios de décarbonation (solaire en toiture, réseau électrique bas-carbone).

**Livrable :** un rendu écrit + une présentation orale de **20 à 30 minutes**, à quatre voix.

## Consignes (cf. `directives_presentation/`)

- Rendre la présentation claire, avec du **storytelling**
- Prévoir des **tableaux/graphiques parlants**
- **Expliquer les méthodologies** utilisées, **chiffrer les résultats**
- **Préparer le speech** — chacun doit maîtriser sa partie, pas seulement la lire

Le rendu suit la structure imposée (illustrée par l'exemple fourni dans `directives_rendu/`) :
**I. Contexte → II. Méthodologie → III. Résultats chiffrés → IV. Scénarios → V. Recommandations**

## Organisation du repo

```
Article_de_Recherche_BigData/
├── README.md
├── article/
│   └── paper_2.pdf
├── directives_rendu/
│   ├── screenshoot_1.png
│   └── screenshoote_2.png
├── directives_presentation/
│   ├── DIRECTIVES.png
└── rendu/
    ├── 01_contexte_mohamed.md
    ├── 02_methodologie_merouan.md
    ├── 03_resultats_emmanuel.md
    ├── 04_scenarios_recommandations_lilian.md
    └── graphiques/
        ├── 01_contexte_fig1.png
        ├── 02_methodologie_fig1.png
        ├── 03_resultats_fig1.png
        └── ...
```

Chacun travaille sur **sa branche** (`git checkout -b partie-prenom`), rédige son fichier dans `rendu/`, puis ouvre une pull request vers `main`. moi/Mohamed relit, fusionne, et assemble le tout dans la présentation finale.


**Important — graphiques et tableaux en image :** merci d'exporter chaque tableau/graphique en **fichier image** (PNG, fond blanc, bonne résolution — capture d'écran Excel/Sheets ou export direct) plutôt que de le décrire seulement en texte, et de le déposer dans `rendu/graphiques/` avec un nom explicite (ex. `03_resultats_fig1_comparaison_methodes.png`). Référencez le nom du fichier dans votre `.md`. Ça évite de refaire chaque visuel à l'assemblage que je vais à la fin.

---

## Répartition des tâches

| # | Partie | Responsable | Durée cible | Fichier |
|---|--------|-------------|-------------|---------|
| I | Contexte & enjeux | **Mohamed** | 5–6 min | `01_contexte_mohamed.md` |
| II | Méthodologie | **Merouan** | 6–7 min | `02_methodologie_merouan.md` |
| III | Résultats chiffrés | **Emmanuel** | 6–7 min | `03_resultats_emmanuel.md` |
| IV–V | Scénarios & recommandations | **Lilian** | 6–7 min | `04_scenarios_recommandations_lilian.md` |

Total : ≈ 25 minutes (marge pour les transitions et les questions).

### I. Mohamed — Contexte & enjeux

Poser le problème et la question de recherche, pour que la suite ait un fil conducteur.

- **Pourquoi le sujet compte** : les data centers consomment 1–1,3 % de l'électricité mondiale (2021) et ont émis 330 Mt CO₂ eq en 2020 (0,6 % des émissions mondiales, source IEA). La croissance projetée par l'IA/crypto pourrait pousser la consommation à 620–1050 TWh en 2026.
- **Comment le carbone est censé être mesuré** : GHG Protocol, Scopes 1/2/3, hiérarchie des méthodes (supplier-specific → hybride → average-data → spend-based), obligation de reporting introduite par l'UE en 2024.
- **Les deux angles morts des standards actuels** : (1) le Scope 3 est difficile à mesurer et très hétérogène selon les modèles d'affaires (écarts de déclaration CDP 2023 : 19 % à 91 % selon les entreprises) ; (2) le tout-carbone masque d'autres impacts (toxicité, eau, ressources).
- **La question de recherche / hypothèse de l'étude** : l'ACV peut-elle améliorer la précision du calcul carbone et révéler des impacts environnementaux invisibles aux méthodes classiques ?
- **Graphique/tableau suggéré** : 3 chiffres clés en gros (330 Mt CO₂, 1–1,3 % élec. mondiale, 620–1050 TWh projetés).

### II. Merouan — Méthodologie

Expliquer *comment* l'étude a été construite, pour crédibiliser les résultats qui suivent.

- **L'outil** : SimaPro 10.2, méthode ReCiPe 2016 (midpoint 18 catégories + endpoint 3 catégories), conforme ISO 14040/14044, base ecoinvent 3.11.
- **Le périmètre du système** : unité fonctionnelle = 1 kWh consommé par l'équipement IT, durée de vie 5 ans, PUE 1,88, réseau électrique américain, 3 générations d'équipement (G1 20 % / G2 60 % / G3 20 %). Hors périmètre : alimentation de secours, climatisation, bâtiment, logiciels.
- **L'inventaire** : liste réelle d'équipements fournie par un prestataire IT (chassis, réseau, périphériques, serveurs blade/standard), composition matière estimée par un LLM (GPT-4) puis validée par un expert.
- **Les trois méthodes comparées** et comment chacune calcule le résultat : LCA (inventaire process par process), average-data (masse × facteur d'émission), spend-based (coût d'achat × facteur d'émission).
- **Validation du modèle** : analyse de sensibilité (taux d'utilisation ±20 %), simulation Monte Carlo (1000 itérations, coefficient de variation < 30 % = fiable).
- **Tableau suggéré** : les 3 méthodes et ce que chacune utilise comme donnée d'entrée.

### III. Emmanuel — Résultats chiffrés

C'est le cœur du rendu : présenter et faire parler les chiffres.

- **Le chiffre central** : 0,710 kg CO₂ eq/kWh. Répartition : 67,3 % électricité, 32,7 % équipement (dont 20,9 % pour le seul serveur standard).
- **Où se cache le carbone** : le serveur standard domine aussi l'écotoxicité, la toxicité humaine et la rareté des ressources minérales (à cause du circuit intégré) ; le serveur blade émet 93,8 % de moins par kWh que le serveur standard.
- **Comparaison des 3 méthodes (le résultat le plus parlant du papier)** : LCA 0,710 vs average-data 0,723 (+1,8 %) vs spend-based 1,07 (+40,4 %) kg CO₂ eq/kWh — le spend-based surestime largement.
- **Robustesse** : la sensibilité (±25 % de variation d'usage) ne change pas le classement des contributeurs ; le CV de la simulation Monte Carlo est de 8,08 % pour le réchauffement climatique global, largement sous le seuil de fiabilité de 30 %.
- **Au-delà du CO₂** : impacts santé humaine (2,36×10⁻⁶ DALY/kWh), écosystèmes (3,37×10⁻⁹ species·yr/kWh), ressources (0,047 USD/kWh) — invisibles dans un bilan carbone classique.
- **Graphique indispensable** : bar chart des 3 méthodes (LCA / average-data / spend-based) avec les écarts en %.

### IV–V. Lilian — Scénarios & recommandations

Conclure sur ce qu'on peut *faire* avec ces résultats.

- **Scénario 1 — solaire en toiture** : ~220 panneaux photovoltaïques, déplace 10 % de l'électricité réseau → réduction de 15,9 % (0,710 → 0,597 kg CO₂ eq/kWh). Sur 5 ans : 7645 tonnes de CO₂ évitées (≈ 7668 acres de forêt/an, équivalence EPA).
- **Scénario 2 — réseau "vert"** (mix électrique norvégien, 89 % hydraulique) : réduction de 63,4 % (→ 0,260 kg CO₂ eq/kWh) — le levier le plus efficace.
- **Le trade-off à souligner** : le solaire réduit le CO₂ mais aggrave certains impacts hors carbone (toxicité liée à la fabrication des panneaux) ; les durées de vie diffèrent fortement (IT : 5 ans, solaire : jusqu'à 30 ans, hydro : 100+ ans).
- **Recommandations des auteurs** : éviter le spend-based pour les décisions à enjeu ; prioriser l'efficacité des serveurs standards ; collaborer avec les fournisseurs pour obtenir des données produit ; adopter une approche hybride (reporting GHG + ACV ciblée) ; ne pas ignorer le cycle de vie complet des solutions "vertes".
- **Limites de l'étude** : un seul data center (États-Unis), gray-space/bâtiment exclus, les 3 méthodes comparées partagent le même inventaire ecoinvent (comparaison méthodologique, pas de sources indépendantes).
- **Graphique suggéré** : bar chart des 3 scénarios (référence / +solaire / réseau vert) avec les % de réduction.

---

## Planning suggéré

1. **Chacun rédige sa partie** dans son fichier `rendu/xx_*.md` (texte du speech  + chiffres + graphiques/tableaux)
2. **Pull request** vers `main` une fois la partie relue
3. *moi/Mohamed assemble** les 4 parties dans `presentation_finale.pptx` (ou tout autre format de diapos choisi) 

