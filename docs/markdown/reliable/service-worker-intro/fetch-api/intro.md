# L'API Fetch

![center](./assets/images/fetch_api.svg)

Notes:
L'api fetch interface javascript pour les requetes xhr<br />
peut faire du Get, du post, passer des params<br />
lors d'un fetch, va passer par le service worker = proxy<br />
si event fetch<br />
puis reseau

##==##

# Retourner une réponse personnalisée

![center](./assets/images/fetch_custom_response.svg)

Notes:
Le retour intercepter par SW
utise un respondWith pour retourner réponse, peut être après traitement
##==##

<!-- .slide: class="with-code" -->

# L'API Fetch

### L'API Fetch fournit une interface pour la récupération de ressources

```javascript
self.addEventListener('fetch', function(event) {
  event.respondWith(
    fetch(event.request).then(function(responseFetch) {
      return responseFetch;
    })
  );
});
```

<!-- .element: class="big-code" -->

<br>

Notes:
https://developer.mozilla.org/fr/docs/Web/API/Fetch_API
La méthode fetch() prend un argument obligatoire, le chemin vers la ressource souhaitée. Elle retourne une promesse qui résout la Response de cette requête, qu'elle soit couronnée de succès ou non. Vous pouvez aussi optionnellement lui passer un objet d'options init comme second argument (voir Request.)
