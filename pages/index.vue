<template>
  <div>
    Inject embedded widget below
    <div id="script-nuxt-embed"></div>
  </div>
</template>

<script setup lang="ts">
onMounted(() => {
  window.embedEvfScript = function () {
    !(function (w, d, e, v, id, t, s, x, y) {
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
      'script',
      'http://localhost:3000/bundle.js',  // bundle generated form Nuxt 3 SSG -> npm run generate
      'nuxt-embed-app'
    );
  };

  window.embedEvfScript();
});
</script>
