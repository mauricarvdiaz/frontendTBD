<template>
  <div>
    <header>
      <div class="branding">
        <img class ="logo-small" src="./img/fidget-spinner.svg" />
        <span>Nagevación superior</span>
      </div>
      <nav>
        <a href="#/">Home</a>
        <a href="#/actors">Actores</a>
        <a href="#/films">Peliculas</a>
      </nav>

    </header>

    <main class="container">
      <router-view></router-view>
    </main>
    <footer>
      Taller de base de datos
    </footer>
</div>
</template>

<script>
export default {

}
</script>
