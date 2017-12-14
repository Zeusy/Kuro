#Kuro Bot
[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](https://raw.githubusercontent.com/kanadeko/Kuro/master/LICENSE)
[![Chat / Support](https://img.shields.io/badge/Chat%20%2F%20Support-discord-7289DA.svg?style=flat-square)](https://discord.gg/5g6vgwn)

Kuro est un bot facile à utiliser qui se déplace de plus en plus dans un framework tout en préservant sa facilité d'utilisation. Il se trouve au-dessus de [discord.js](https://github.com/hydrabolt/discord.js/). La version 6+ de NodeJS est ***OBLIGATOIRE***. [Installation de Node.js](https://nodejs.org/en/download/package-manager/)

[> Check this video to see how it works!](https://my.mixtape.moe/pwcrem.webm)

>## v4.1.0 Notes Importantes:
>Cela ne s'applique que si vous effectuez une mise à niveau à partir d'une version précédente.
>Afin de rendre le tchat moins instable et de contribuer avec les limites de données et les >utilisateurs mobiles, les autocollants se comportent maintenant différemment. Les >autocollants sont maintenant téléchargés sur [safe.moe](https://safe.moe) et utilisés dans >une embed. En utilisant des embeds, kuro peut maintenant éditer votre message pour >afficher l'autocollant au lieu de le supprimer et d'en envoyer un nouveau. Même si ces >embeds sont laids, cela permet à tout le monde de voir votre autocollant plus rapidement en >permettant la mise en cache de l'URL du côté de Discord.
>
>Donc, si vous effectuez une mise à niveau vers une nouvelle version, exécutez `!s migrate` pour migrer vos autocollants vers le nouveau système d'intégration.

## Installation:
1. Assurez-vous que node est installé
2. Lancer `npm i -g kuro-cli`
3. Exécuter `kuro-cli`
4. Follow the instructions on screen

[kuro-cli](https://github.com/Pitu/kuro-cli) est un utilitaire qui va installer et gérer votre installation Kuro. Chaque fois qu'une nouvelle version est disponible, vous pouvez lancer `kuro-cli` et télécharger, mettre à jour, mettre à jour les dépendances et redémarrer automatiquement. Certaines options ne sont pas encore couvertes sur le cli, donc vous pouvez aller de l'avant et ouvrir `config.json`  pour les regarder et les modifier si vous le souhaitez. 

Si vous ne voulez pas utiliser `kuro-cli`, il vous suffit de cloner le repo, `npm install`, de renommer `config.sample.json` en `config.json`et de modifier ses valeurs avec vos données.

## Modules:
Cette nouvelle mise à jour apporte chaque commande sous la forme de modules séparés. À l'intérieur de chaque module, vous pouvez créer ce que vous voulez, et vous pouvez l'exécuter en appelant le nom du module sans l'extension. Il y a un exemple de module prêt à être dupliqué appelé `base.js`.

Exemple d'un module simple sans dépendances qui renvoie le nombre de membres du serveur sur lequel vous envoyez la commande:
```javascript
exports.run = function(msg, args) {
  msg.delete()
  msg.channel.send('', {
    'embed': {
      'title': msg.guild.name,
      'description': `Nombre de membres: ${msg.guild.memberCount}`,
      'color': 15473237
    }
  })
}
```

Assez facile.
Si vous voulez que inclure un module que vous avez fait,  envoyez un PR à [^1] [Pitu](https://github.com/Pitu) avec votre module.

[^1]: Créateur de ***Kuro***.

## Modules groupés

Chaque module a des instructions détaillées dans leurs propres fichiers. Jetez y un oeil pour plus de détails sur la façon de les utiliser.

- `anime <name of the anime>` Affiche la première occurrence de l'anime recherché sur kitsu.io et renvoie un résumé de celui-ci (en anglais).

- `emote [emote]` Affiche des informations sur une emote personnalisée.

- `eval [expression]` Un module pour évaluer les expressions. N'utilisez pas des choses dangereuses à moins d'être sûr de ce que vous faites.

- `eyes` Un module qui édite un message pour ajouter l'effet des yeux animés. Vous devriez probablement mettre à jour le nom emoji si vous n'êtes pas sur le serveur de Pilar.

- `flip <this is amazing>` = "sllɐqǝzɐɯɐ sı sıɥʇ" 

- `getcommand [module]` Envoie la source du module spécifié au tchat. Ex: `!getcommand base` renvoie le contenue de `base.js` dans le tchat.

- `gifspeed [url]` Supprime le délai entre les images de l'URL gif donnée et le télécharge.

- `google <some stupid question>` Crée un lien vers Google avec votre requête quand quelqu'un pose des questions stupides.

- `mal` Imprime des informations sur votre nom d'utilisateur MyAnimeList.

- `manga <nom du manga>` Affiche la première occurrence du manga recherché sur kitsu.io et retourne un résumé de celui-ci

- `members` Affiche le nombre de membres du serveur.

- `ping` Outil simple pour vérifier le délai entre votre bot et Discord.

- `playing [message]`Change ton statut `playing` sur Discord pour la chaîne spécifiée. (Notez que vous ne pourrez pas le voir en raison d'une limitation Discord).

- `purge [nombre de messages]` Récupère le nombre de messages fournis par chat et supprime ceux qui sont à vous.

- `reboot` Redémarre le Kuro. (Fonctionne uniquement si vous utilisez pm2 | forever).

- `reload` Recharge tous les modules (Utile en cours de développement).

- `react [message]` Réagir au dernier message avec des caractères régionaux. a-z 0-9, pas d'espaces.

- `regional [message]` Envoie un message en utilisant le caractère régional emojis.

- `s [nom] | [add|del|ren]` Un module pour gérer les autocollants comme Telegram. Téléchargez un autocollant avec un nom donné, puis faites kuro le coller lorsque vous déclenchez la commande.

- `smug` Affiche des filles anime à l'air suffisant avec des regards condescendants sur leurs visages.

- `stats` Affiche un embed avec des statistiques.

- `status [online|idle|dnd|offline]` Le statut que vous voulez afficher lorsque vous êtes hors ligne, car l'utilisation de Kuro fera penser à Discord que vous êtes toujours en ligne.

- `tag [name] | [add|del|ren]` Enregistre le texte donné dans une balise pour une utilisation ultérieure. Par exemple `tag add kuro https://github.com/kanadeko/Kuro` afficherait ` https://github.com/kanadeko/Kuro` à chaque fois que je fais `tag kuro`

- `tl` Essaie de traduire le dernier message en anglais.

- `uptime` Affiche la durée d'exécution du bot.

- `user <@user>` Affiche des informations sur l'utilisateur marqué

  ​
  ![Kuro Bot](http://i.imgur.com/ohS1PwH.png)