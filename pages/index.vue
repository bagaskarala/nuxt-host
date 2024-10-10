<template>
  <div>
    Inject embedded widget below
    <div id="script-nuxt-embed"></div>
  </div>
</template>

<script setup lang="ts">
onMounted(() => {
  window.embedEvfScript = function (params) {
    !(function (w, d, v, u, e, id, t, s, x, y) {
      id = 'evf-embed-widget',
        e = 'script';
      w.__NUXT__ = w.__NUXT__ || {}; w.__NUXT__["evf-widget"] = { config: { public: {}, app: { baseURL: "/", buildId: "", buildAssetsDir: "/", cdnURL: "" } } };

      w.evf = {
        originalUrl: u,
      };

      x = d.createElement('div');
      x.id = id;
      x.innerHTML = 'Loading Widget...';
      y = d.getElementById('script-nuxt-embed');
      y.parentNode.insertBefore(x, y);

      t = d.createElement(e);
      t.async = !0;
      t.src = v;
      s = d.getElementsByTagName(e)[0];
      s.parentNode.insertBefore(t, s);
    })(
      window,
      document,
      'https://cdn-staging.gabung.id/form-builder/embed/e54e4849/bundle.js',
      params.url
    );
  };

  window.embedEvfScript({ url: 'https://evm-form-fe-embedded.fb.evermosa2z.com/alat-cukur-naga-keren?subdomain=apple' });
});
</script>
