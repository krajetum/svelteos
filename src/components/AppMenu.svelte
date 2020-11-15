<script>
  import { scale } from "svelte/transition";
  import { clickOutside } from "../directives/clickOutside.js";
  let menu = false;

</script>

<style>
  .app-icon {
    width: 3rem;
    height: 3rem;
    padding: 0rem;
    outline: none;
    color: white;
    background: transparent;
    border: 0;
    cursor: pointer;
    transition: background-color 75ms linear;
  }
  .app-icon:hover {
    background-color: rgba(255, 255, 255, 0.185);
  }
  .app-menu {
    position: relative;
    display: inline-block;
  }
  .app-menu-content {
    position: absolute;
    background-color: #292929;
    z-index: 1;
    bottom: 100%;
    height: var(--menu-height, 40vh);
    overflow-y: auto;
  }
  ul,
  li {
    padding: 0;
    margin: 0;
    list-style: none;
  }
  button {
    padding: 0;
    margin: 0;
    border: 0;
    background: transparent;
    cursor: pointer;
  }
  .wrapper {
    display: inline-flex;
    height: 100%;
  }
  .applications {
    overflow-y: auto;
    overflow-x: hidden;
  }
  .mainbar {
    display: flex;
    flex-direction: column-reverse;
  }
  .app {
    width: 25rem;
  }
  .app button {
    padding: 0 1rem;
    width: 100%;
    color: white;
    font-weight: normal;
    text-align: left;
    height: 3rem;
    line-height: 3rem;
    vertical-align: middle;
  }
  .app button span {
    padding: 0 0.75rem;

  }
  .app button:hover {
    background-color: rgba(255, 255, 255, 0.185);
  }
  .widgets {
    padding: 0.5rem 0.5rem;
    display: grid;
    grid-template-rows: 8rem 8rem 8rem;
    grid-template-columns: 8rem 8rem 8rem;
  }
  .widgets .widget {
    width: 8rem;
    height: 8rem;
    text-align: center;
    color: white;
    background-color: rgb(3, 125, 173);
    transition: background-color 100ms linear;
    cursor: pointer;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .widgets .widget .title {
    line-height: 1rem;
    font-size: 1rem;
  }
  .widgets .widget:hover {
    background-color: rgba(0, 143, 199, 0.952);
  }
</style>

<div class="app-menu" use:clickOutside on:click_outside={() => (menu = false)}>
  <button class="app-icon" on:click={() => (menu = !menu)}>
    <i class="fas fa-home fa-lg" />
  </button>
  {#if menu}
    <div
      class="app-menu-content"
      transition:scale={{ duration: 200, start: { x: 0, y: 0 } }}>
      <div class="wrapper">
        <div class="mainbar">
          <button class="app-icon">
            <i class="fas fa-power-off fa-lg" />
          </button>
          <button class="app-icon"> <i class="fas fa-home fa-lg" /> </button>
          <button class="app-icon"> <i class="fas fa-cog fa-lg" /> </button>
        </div>
        <div class="applications">
          <ul>
            <li class="app">
              <button><i class="fas fa-folder" /> <span>Folder</span> </button>
            </li>
            <li class="app">
              <button><i class="fas fa-calculator" /> <span>Calculator</span> </button>
            </li>
          </ul>
        </div>
        <div class="widgets">
          <div class="widget">
            <div>
              <i class="fas fa-power-off fa-2x" />
              <div class="title">Home</div>
            </div>
          </div>
          <div class="widget">
            <div>
              <i class="fas fa-power-off fa-2x" />
              <div class="title">Home</div>
            </div>
          </div>
          <div class="widget">
            <div>
              <i class="fas fa-power-off fa-2x" />
              <div class="title">Home</div>
            </div>
          </div>
          <div class="widget">
            <div>
              <i class="fas fa-power-off fa-2x" />
              <div class="title">Home</div>
            </div>
          </div>
        </div>
        <div class="widgets">
          <div class="widget">
            <div>
              <i class="fas fa-power-off fa-2x" />
              <div class="title">Home</div>
            </div>
          </div>
          <div class="widget">
            <div>
              <i class="fas fa-power-off fa-2x" />
              <div class="title">Home</div>
            </div>
          </div>
          <div class="widget">
            <div>
              <i class="fas fa-power-off fa-2x" />
              <div class="title">Home</div>
            </div>
          </div>
          <div class="widget">
            <div>
              <i class="fas fa-power-off fa-2x" />
              <div class="title">Home</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  {/if}
</div>
