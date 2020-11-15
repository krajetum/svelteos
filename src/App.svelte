<script lang="ts">
	
  import AppMenu from "./components/AppMenu.svelte";
import Clock from "./components/Clock.svelte";
  import GlobalStyle from "./GlobalStyle.svelte";
</script>

<style lang="postcss">
  .appbar {
    background-color: #141414;
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    display: flex;
    flex-wrap: nowrap;
    line-height: 2.5rem;
    vertical-align: middle;
  }
  .app-section {
    flex-grow: 1;
  }

  main {
    height: 100%;
    margin-bottom: 2.5rem;
    background: url("/images/wallpaper.jpg");
    background-repeat: no-repeat;
    background-size: cover;
  }
</style>

<GlobalStyle />

<nav class="appbar">
  <div class="app-section">
    <AppMenu></AppMenu>
  </div>
  <div class="notification-section">
    <Clock />
  </div>
</nav>

<main />
