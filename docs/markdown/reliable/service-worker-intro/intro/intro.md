# Service Worker

![center](./assets/images/service_worker_explain.svg)

Notes: Un service worker est un proxy programmable côté client entre la webapp et l'exterieur

##==##

<!-- .slide: data-background="./assets/images/grid_background.svg" -->

<div class="grid-worker">
    <div class="cell-1">
        <h1>Non bloquant</h1>
        MAIN THREAD
        <br>≠
        <br>
        SERVICE WORKER
    </div>
    <h1 class="cell-2">Pas accès au dom</h1>
    <h1 class="cell-3">Asynchrone</h1>
    <div class="cell-4">
        <h1>Sécurisé</h1>
        HTTPS uniquement
    </div>
</div>

Notes:
Thread différente du script principal donc non-bloquant<br />
Un service worker fonctionne dans le contexte d'un WorkerGlobalScope :<br />
Pas d’accès au DOM<br />
Asynchrone (Pas de localstorage ou de XHR synchrone)
https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API

##==##

# Support

![center h-600](./assets/images/caniuse_serviceworker.png)

<br>
<h2 class="center"><a href="https://jakearchibald.github.io/isserviceworkerready/" target="_blank">Is Service Worker Ready ?</a></h2>
<br>

Notes:
MàJ: 2018-09-18 - https://caniuse.com/#feat=serviceworkers
