# ft_irc

Bienvenue dans **ft_irc** — un serveur Internet Relay Chat (IRC) simple mais complet, écrit en C++, conforme aux spécifications des RFC IRC.

Ce projet a été développé dans le cadre de l’école 42 et te permet de comprendre comment fonctionne un serveur de chat bas-niveau : sockets TCP, multiplexage, parsing de commandes, gestion des clients et des channels.

---

## Qu’est-ce que c’est ?

IRC est un protocole de communication en texte permettant à des utilisateurs de discuter en temps réel dans des salons (“channels”) ou en messages privés.  
Ce serveur est capable de :

- accepter plusieurs clients simultanément
- gérer des channels et les rejoindre/quitter
- dispatcher les messages vers tous les membres d’un channel
- répondre aux commandes IRC usuelles

Toutes les parties critiques (connexion, parsing, gestion des commandes) sont codées à la main, sans dépendances externes.

---

## Fonctionnalités clés

- Connexion TCP fonctionnelle avec mot de passe  
- Support de plusieurs clients en même temps  
- Gestion de channels et d’opérateurs  
- Parsing des commandes IRC avec réponses conformes aux RFC  
- Messages publics et privés  
- Gestion propre des déconnexions
- Transfert des fichiers

La logique est répartie entre plusieurs classes : `Server`, `Client`, `Channel`, ce qui rend le code relativement lisible et maintenable.

---

## Protocoles suivis

Ce serveur suit les spécifications principales du protocole IRC définies dans :

- **RFC 1459 — Internet Relay Chat Protocol**
- **RFC 2812 — Internet Relay Chat: Client Protocol**

Cela signifie que tu peux te connecter avec n’importe quel client IRC standard sans problème.

---

## Compilation

Pour compiler le serveur, rien de plus simple :

```
make
./ircserv <PORT> <PASSWORD>
```

Par exemple:
```
./ircserv 6667 mypassword
```

Pour l'authentification en tant que client il suffit de se connecter avec irssi ou netcat:
```
netcat -C localhost <PORT>
PASS <PASSWORD>
NICK <NICK>
USERNAME <USERNAME> <*> <*> <:REAL NAME>
JOIN #test_channel
PRIVMSG #test_channel Hello world !
```

-C option envoie ```\r\n``` sur la touche ```Enter```

---

## Les commandes existantes

- PASS
- NICK
- USER
- PRIVMSG
- NOTICE
- JOIN
- PART
- TOPIC
- MODE ```+-iklot```
- PING / PONG
- WHOIS
- KICK
- INVITE
- WHO
- NAMES
- LIST
- QUIT / EXIT

## Auteurs

- [Robzzz95](https://github.com/Robzzz95)
- [test-Banal](https://github.com/test-Banal)
- [Min0laa](https://github.com/Min0laa)
