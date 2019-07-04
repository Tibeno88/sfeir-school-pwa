<!-- .slide: class="full-center" -->

# Background-sync

<ol>
  <li>Sortir le téléphone de la poche</li>
  <li>Envoyer quelque chose sur internet</li>
  <li>Remettre le téléphone dans la poche</li>
  <li>Reprendre la vie</li>
  <li>Recommencer 🙃</li>
<ol>

<br /><br /><br /><br />
![h-300](./assets/images/wifi_no-wifi.png)
Connexion toujours disponible ?

Notes:
On adore internet => vidéo de chats qui ont peur des concombres<br />
mais pas toujours devant un écran<br />

offline ? interessant d'envoyer quand reseau revient

##==##

<!-- .slide: class="with-code" -->

# Background-sync

main.js

```javascript
navigator.serviceWorker.ready.then(function(swRegistration) {
  return swRegistration.sync.register('myFirstSync');
});
```

<!-- .element: class="big-code" -->

service-worker.js

```javascript
self.addEventListener('sync', function(event) {
  if (event.tag == 'myFirstSync') {
    event.waitUntil(doSomeStuff());
  }
});
```

<!-- .element: class="big-code" -->

Notes:

##==##

# Utilisabilité

![h-600](./assets/images/caniuse-background-sync.png)

Notes: 03/07/2019
