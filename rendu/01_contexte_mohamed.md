# I. Contexte & enjeux — Mohamed

*Durée cible : 5–6 min · Source : Smith, M., Mann, M. & Lal, P. (2026). "Carbon Accounting and Beyond: An Evidence-Based Life Cycle Assessment of the Environmental Impacts of Data Center IT Equipment." Sustainability, 18(11), 5671.*

## Speech

### 1. Pourquoi ce sujet compte

Les data centers sont devenus une infrastructure critique — cloud, IA, stockage — et leur facture énergétique explose. En 2020, l'International Energy Agency (IEA) estimait leurs émissions à 330 millions de tonnes de CO₂ équivalent, soit 0,6 % des émissions mondiales de gaz à effet de serre. En 2021, data centers et réseaux de transmission représentaient déjà 1 à 1,3 % de la consommation électrique mondiale.

Ce qui inquiète, c'est la trajectoire : entre 2015 et 2023, la charge de travail des data centers a augmenté leur consommation énergétique de 20 à 40 %. L'IEA projette qu'en 2026, la consommation électrique liée aux data centers, à l'IA et aux cryptomonnaies atteindra entre 620 et 1050 TWh — jusqu'à 590 TWh de plus qu'en 2022. *(→ figure 1)*

### 2. Comment le carbone est censé être mesuré

Face à cette croissance, l'Union européenne a introduit en 2024 une obligation de reporting énergie/émissions pour les opérateurs de data centers (Energy Efficiency Directive), avec un objectif de neutralité climatique en 2030.

Le cadre de référence utilisé par la quasi-totalité des entreprises du secteur (Amazon, Microsoft…) est le **GHG Protocol**, qui organise les émissions en trois périmètres :
- **Scope 1** — émissions directes (combustibles, groupes électrogènes)
- **Scope 2** — électricité, chauffage, refroidissement achetés
- **Scope 3** — toute la chaîne de valeur : achats, biens d'équipement, transport, fin de vie

Pour calculer les émissions liées aux achats (catégorie Scope 3 la plus pertinente pour l'équipement IT), le GHG Protocol propose 4 méthodes, de la plus précise à la plus grossière : **supplier-specific → hybride → average-data → spend-based**. Plus on descend dans cette hiérarchie, moins la mesure reflète la réalité physique du matériel — et c'est précisément le problème que l'étude va documenter.

### 3. Deux angles morts des standards actuels

**Premier angle mort : le Scope 3 échappe largement au contrôle.** La majorité des fabricants ne fournissent pas de données d'émissions spécifiques à leurs produits, et les entreprises reposent alors sur des méthodes moyennées peu précises. La désagrégation est d'autant plus difficile que les modèles d'affaires du secteur sont hétérogènes — colocation (Equinix, CyrusOne) vs cloud intégré (AWS, Azure). Résultat : d'énormes écarts de transparence. Dans les déclarations CDP 2023, la part du Scope 3 dans les émissions totales déclarées varie de 19 % (CyrusOne) à 91 % (NTT Data) selon les entreprises. *(→ figure 2)* Seulement 18 % des entreprises rapportent effectivement leurs émissions Scope 3.

**Second angle mort : le tout-carbone masque le reste.** En se concentrant sur le CO₂, les standards GHG ignorent d'autres impacts environnementaux majeurs de la fabrication IT — toxicité, consommation d'eau, épuisement de ressources minérales rares (métaux précieux des circuits intégrés). Or ces impacts peuvent être disproportionnés par rapport au poids carbone d'un composant.

La littérature existante reste par ailleurs limitée : elle s'appuie surtout sur des modèles théoriques ou des données secondaires, rarement sur des données empiriques équipement par équipement, et aucune étude publiée n'avait encore comparé systématiquement l'analyse de cycle de vie (ACV) aux méthodes comptables GHG sur un même data center.

### 4. La question de recherche

C'est le point de départ de cette étude : **l'analyse de cycle de vie (ACV / LCA) peut-elle mesurer les émissions carbone avec plus de justesse que les méthodes comptables classiques — et révéler, au passage, des impacts environnementaux que le CO₂ seul ne montre jamais ?**

Pour y répondre, les auteurs vont : comparer un modèle ACV empirique aux méthodes average-data et spend-based du GHG Protocol ; tester la robustesse de ce modèle (sensibilité, incertitude) ; puis explorer des scénarios de décarbonation (solaire, réseau électrique bas-carbone).

*→ Merouan enchaîne sur la méthodologie de l'étude.*

## Chiffres clés à afficher

| Chiffre | Valeur | Contexte |
|---|---|---|
| Émissions data centers | 330 Mt CO₂ eq (2020) | 0,6 % des émissions mondiales de GES |
| Part électricité mondiale | 1–1,3 % (2021) | data centers + réseaux de transmission |
| Consommation projetée 2026 | 620–1050 TWh | +160 à +590 TWh vs 2022 (IA, crypto) |
| Écart de déclaration Scope 3 (CDP 2023) | 19 % à 91 % | CyrusOne vs NTT Data |
| Entreprises qui rapportent leur Scope 3 | 18 % | source : littérature citée par l'étude |

## Graphiques / tableaux

1. **`graphiques/01_contexte_fig1_chiffres_cles.png`** — 3 stat-tiles : 330 Mt CO₂ eq / 1–1,3 % électricité mondiale / 620–1050 TWh projetés. Sert d'accroche visuelle en ouverture de partie.
2. **`graphiques/01_contexte_fig2_scope3_cdp.png`** — Bar chart : part du Scope 3 dans les émissions totales déclarées au CDP 2023 (CyrusOne 19 %, Equinix 35 %, NTT Data 91 %). Illustre l'hétérogénéité du reporting actuel.

## Version HTML

Une version mise en page de cette partie (mêmes contenus, même identité visuelle que la présentation finale) est disponible dans [`01_contexte_mohamed.html`](./01_contexte_mohamed.html).
