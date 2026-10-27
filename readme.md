<p align="center">
  <img src="docs/logo/meecole-icon-256.png" alt="Meecole" width="128" />
</p>

<h1 align="center">Meecole 1.0</h1>

<p align="center">La gestion d’école privée, sur vos PC, sans internet.<br />Par Guendouze Co.</p>

---

Meecole tient le registre d’une école privée, d’un centre de formation ou d’une école de langues : les élèves, les classes et les groupes, l’appel, l’accueil, les mensualités et les reçus, les factures, les honoraires des professeurs, et tous les documents à imprimer avec l’en-tête de l’école. Tout reste sur le PC principal de l’école ; les autres postes s’y connectent par le réseau local.

La version 1.0 est la première que nous considérons comme complète. Elle change surtout l’allure de l’application et la façon de garder son compte.

## Ce qui change en 1.0

**Une application qui ressemble à du papier.** Les écrans prennent l’aspect d’un registre : feuilles légèrement texturées, filets, titres d’imprimerie. Ce qui demande votre attention est passé au surligneur, comme on le ferait sur un rapport : rouge pour l’urgent et l’argent dû, orange pour ce qui arrive, jaune pour ce qui reste à faire. Il reste deux thèmes, Papier et Nuit, et vous pouvez choisir vos propres couleurs.

**Un écran d’accueil qui se lit comme un rapport.** Aujourd’hui présente les séances, la trésorerie du mois, les points d’attention et le journal, en sections numérotées.

**Votre compte vous suit.** « Rester connecté » est coché d’office : plus besoin de se reconnecter après une mise à jour ou une coupure de courant. Un mot de passe oublié ne bloque plus personne : l’administration donne un code à 8 chiffres, et l’administrateur dispose d’une clé de récupération remise à la création de l’école.

**Plusieurs écoles sur un même PC.** Chaque école a son dossier, et toutes restent joignables par les autres postes. La liste des écoles affiche toujours celles gardées sur le PC ; on ne peut plus en perdre une de vue par erreur.

**Plus simple au quotidien.** Le pointage s’écrit en toutes lettres, le menu du bas se range et se trie à la souris, le clic droit dans les tableaux colore une ligne ou surligne une case, les factures s’impriment aussi en arabe, et la liste des élèves se filtre par groupe.

Le détail complet se trouve dans le [journal des versions](CHANGELOG.md).

## Installer

1. Téléchargez `Meecole-installateur.exe` depuis cette page et lancez-le sur le PC principal de l’école.
2. Choisissez « Créer une école sur ce poste » et suivez les étapes : l’établissement, l’en-tête des documents, votre activité, les modules, l’année scolaire et le compte administrateur.
3. **Notez la clé de récupération** qui s’affiche à la fin. Elle n’est montrée qu’une fois.
4. Sur les autres postes, installez Meecole et choisissez « Rejoindre une école du réseau ».

Si vous utilisiez déjà Meecole, la mise à jour se fait d’elle-même : vos données, vos comptes et vos réglages sont gardés. Pensez ensuite à créer la clé de récupération de votre école dans Mon compte.

Windows 10 ou 11. Sur le PC principal, autorisez Meecole dans le pare-feu quand Windows le demande (port 4100, puis 4102 et suivants pour chaque école en plus, et 4101 pour la recherche des écoles).

## Besoin d’aide ?

Le guide complet est dans l’application (bouton « ? » en haut à droite), aussi en PDF.

Assistance Guendouze Co. : support@guendouze.com · WhatsApp 0791 52 65 06

---

<details>
<summary>Pour les développeurs</summary>

Node.js 22 ou plus récent et Rust sont nécessaires. Une fois, dans ce dossier : `npm install`.

| Commande | Rôle |
|---|---|
| `cargo xtask run` | Vide les caches web, reconstruit tout et ouvre l’application de bureau. |
| `cargo xtask dev` | Application de bureau avec rechargement à chaud. |
| `cargo xtask web` | La même application dans le navigateur, http://localhost:5173. |
| `cargo xtask check` | Vérification des types, tests et compilation du bureau. |
| `cargo xtask package` | Construit l’installateur dans `target/release/bundle/`. |

`server/` le serveur de l’école (Node, Fastify, SQLite), `web/` les écrans (Svelte 5), `desktop/` le bureau (Tauri 2), `tests/` les tests (`npm test`).

</details>
