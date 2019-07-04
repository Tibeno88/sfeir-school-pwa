## Devtools

# Jouer avec le cycle de vie

![h-600](./assets/images/lifecycle-console.png)

Notes:
"update on reload" => au reload, force le SW à se MAJ et s'activer
Unregister => supprimer le SW
STOP + Start
Bypass for network => ignore le SW et passe par réseau
Offline: simule absence reseau
##==##

<!-- .slide: class="with-code" -->

# Event API

### Elle permet d'étendre la durée de vie de l'évènement

```javascript
self.addEventListener('install', function(event) {
  event
    .waitUntil
    //Promise
    ();
});
```

<!-- .element: class="big-code" -->

Notes: Un event est asynchrone <br />
Normalement, Se termine avant que l'on ai fini les actions a faire<br/>
Fixé avec waitUntil, attendre la résolution de la dernière promise a l'interieur avant de terminer l'event
##==##

# Installation

![center h-600](./assets/images/sw_life_cycle_installing.png)

Notes:
Passe dedans 1 seule fois<br/>
SkipWaiting => aller directement à l'étape d'installation / sans attendre que le client soit fermé

##==##

<!-- .slide: class="with-code" -->

# skipWaiting

### Force le service en attente à devenir le service worker actif

```javascript
self.addEventListener('install', function(event) {
  // The promise that skipWaiting() returns
  // can be safely ignored.
  self.skipWaiting();
  // Perform any other actions required for your
  // service worker to install, potentially inside
  // of event.waitUntil();
});
```

<!-- .element: class="big-code" -->

<br>
<a target="_blank" href="https://cdn.rawgit.com/jakearchibald/80368b84ac1ae8e229fc90b3fe826301/raw/ad55049bee9b11d47f1f7d19a73bf3306d156f43/index-v3.html" >Demo</a>
<!-- .element: class="center" -->

Notes:
Force le SW a devenir le SW actif<br />
skipWaiting() signifie aussi que le nouveau SW passe en étape d'activation<br />
Peut y avoir des changement de comportement + bugs<br />
A utiliser surtout si casse rien

##==##

# Activation

![center h-600](./assets/images/sw_life_cycle_activating.png)

##==##

<!-- .slide: class="with-code" -->

# claim

### Force l’activation du service worker en attente ⇢ qui devient le worker actif de la page

```javascript
self.addEventListener('activate', function(event) {
  event.waitUntil(self.clients.claim());
});
```

<!-- .element: class="big-code" -->

<br>

Notes:
self.clients.claim() force le SW a devenir le SW actif<br />

- controle tous clients ouvert sans reload
