const CACHE_NAME = 'trousse-outils-v1';
const urlsToCache = [
  '/',
  '/index.html',
  '/manifest.json'
];

self.addEventListener('install', event => {
  event.waitUntil(
    caches.open(CACHE_NAME).then(cache => {
      return cache.addAll(urlsToCache).catch(() => {
        // Certains fichiers peuvent ne pas être disponibles offline
        return cache.add('/index.html');
      });
    })
  );
});

self.addEventListener('fetch', event => {
  // Les liens externes s'ouvrent toujours en ligne
  if (event.request.url.includes('https://') && !event.request.url.includes(self.location.origin)) {
    return; // Laisse passer
  }

  event.respondWith(
    caches.match(event.request).then(response => {
      return response || fetch(event.request).then(response => {
        if (!response || response.status !== 200 || response.type !== 'basic') {
          return response;
        }
        const responseToCache = response.clone();
        caches.open(CACHE_NAME).then(cache => {
          cache.put(event.request, responseToCache);
        });
        return response;
      }).catch(() => {
        return caches.match('/index.html');
      });
    })
  );
});
