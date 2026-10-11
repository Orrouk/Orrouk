---
mission_id: MISSION-MIGRATION-MISSIONS-GITHUB-001
status: PILOTE
authority: github
repository: Orrouk/Orrouk
branch_preparation: ipcra-mission-governance
source_systems: [google_drive]
protected:
  - Epub
  - governed_vaults
  - source_corpora
  - publication_products
---

# MISSION-MIGRATION-MISSIONS-GITHUB-001

## But
Établir proprement la séparation suivante :

**GitHub = missions, agents, procédures, schémas, tests.**  
**Drive = sources, corpus, manuscrits, recherches, médias, produits, livrables et journaux humains.**  
**Obsidian = relations, MOC, fiches atomiques et navigation documentaire.**

La mission prépare la migration des définitions de missions réutilisables actuellement dispersées dans Drive vers une couche GitHub versionnée, sans déplacer les contenus documentaires.

## Priorité initiale
Commencer par la chaîne active :
1. `MISSION-AUDIT-INDEXATION-CORPUS-001`
2. `MISSION-RECLASSEMENT-IPCRA-DRIVE-001`
3. `MISSION-CARTOGRAPHIE-VOUTES-GOUVERNEES-IPCRA-001`
4. couche de `CONCILIATION IPCRA`
5. registre des outils et règles de maturité associées.

## Sources à consulter avant toute écriture
Dans Google Drive, retrouver et lire au minimum :
- `MISSION-AUDIT-INDEXATION-CORPUS-001`
- `INDEX-DOCUMENTAIRE-CORPUS-001`
- `MISSION-CARTOGRAPHIE-VOUTES-GOUVERNEES-IPCRA-001`
- `REGISTRE-VOUTES-GOUVERNEES-IPCRA-001`
- `MISSION-RECLASSEMENT-IPCRA-DRIVE-001`
- `08_JOURNAL_MIGRATION_IPCRA_001`
- `4_TOOLS/00_REGISTRE_OUTILS`
- les fiches outils PILOTE / EPROUVE pertinentes;
- les passations récentes qui modifient les règles de ces missions.

## Travail demandé

### Phase A — Inventaire
1. Inventorier les définitions de missions actives ou réutilisables dans Drive.
2. Distinguer :
   - mission canonique active;
   - mission pilote;
   - mission réutilisable éprouvée;
   - mission ponctuelle terminée;
   - rapport/résultat qui n'est pas une mission;
   - doublon ou version supersédée.
3. Ne pas migrer mécaniquement tous les fichiers commençant par `MISSION-`.

### Phase B — Normalisation
Pour chaque mission retenue :
1. conserver exactement son `mission_id`;
2. extraire but, entrées, autorités, contraintes, procédure, critères de succès et passation;
3. noter la provenance Drive (titre + ID/URL si disponible);
4. identifier les dépendances vers d'autres missions, registres ou voûtes;
5. expliciter les systèmes d'autorité;
6. inscrire le statut de maturité.

### Phase C — Écriture GitHub
Créer les fichiers canoniques sous :
- `ipcra/missions/audit/`
- `ipcra/missions/reclassement/`
- `ipcra/missions/cartographie/`
- `ipcra/missions/conciliation/`
- `ipcra/agents/` pour les contrats d'agents réutilisables;
- `ipcra/tests/` pour les scénarios de vérification lorsque pertinents.

Ne pas copier dans GitHub les corpus, manuscrits, exports Facebook, images, EPUB, rapports clients ou produits éditoriaux.

### Phase D — Miroirs Drive
Après qu'une mission GitHub a été vérifiée :
1. conserver l'original Drive comme historique tant que la migration n'est pas validée;
2. créer ou recommander une fiche miroir courte dans `4_TOOLS` contenant :
   - mission_id;
   - fonction;
   - statut;
   - lien GitHub canonique;
   - dernières validations;
   - corpus où elle a été testée.
3. ne jamais maintenir deux versions actives divergentes sans signalement.

### Phase E — Tests
Pour la chaîne Audit → Reclassement → Conciliation :
1. vérifier que chaque mission peut retrouver ses sources Drive;
2. vérifier qu'aucune mission ne dépend implicitement d'un texte présent seulement dans un ancien prompt de conversation;
3. vérifier les protections Epub et voûtes gouvernées;
4. vérifier l'absence de suppression automatique non autorisée;
5. vérifier la règle d'ambiguïté / ARBITRAGE_REQUIS;
6. vérifier que les trois missions peuvent fonctionner séquentiellement sans double traitement.

## Invariants
- aucune source ou produit ne quitte Drive dans cette mission;
- aucune suppression;
- aucun changement de canon éditorial;
- aucune réécriture des œuvres;
- GitHub ne devient pas un entrepôt documentaire;
- les identifiants Drive sont des références, pas des copies de contenu;
- toute divergence substantielle est signalée.

## Livrables
1. arborescence GitHub IPCRA opérationnelle;
2. missions prioritaires migrées;
3. index GitHub des missions actives;
4. liste des missions Drive restant à évaluer;
5. liste des doublons/supersédés;
6. rapport de test;
7. recommandations de fiches miroirs Drive;
8. passation finale avec arbitrages éventuels.

## Critère de fermeture
La mission est terminée lorsque la chaîne Audit → Reclassement → Conciliation peut être lue et versionnée depuis GitHub, tout en continuant à travailler sur les sources et produits Drive, sans ambiguïté sur l'autorité ni perte de provenance.

## Règle d'arbitrage
Si le dépôt `Orrouk/Orrouk` est jugé inadéquat comme dépôt permanent pour IPCRA, **ne pas disséminer les fichiers ailleurs** : marquer `ARBITRAGE_REQUIS — dépôt GitHub permanent` et proposer un dépôt dédié. La préparation présente peut rester sur la branche `ipcra-mission-governance` jusqu'à décision.
