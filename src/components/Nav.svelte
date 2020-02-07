<script>
  export let segment;
  // import { Button, Icon } from 'svelte-mui/src';
  import Socials from "../components/Socials.svx";
</script>

<style>
  nav {
    border-bottom: 1px solid rgba(255, 62, 0, 0.1);
    font-weight: 300;
    padding: 0 1em;
  }
  nav {
    display: grid;
    grid-template-columns: 1 1;
  }
  /* ul {
    margin: 0;
    padding: 0;
  } */
  /* clearfix */
  /* ul::after {
    content: "";
    display: block;
    clear: both;
  } */
  li {
    display: block;
    float: left;
  }

  .selected {
    position: relative;
    display: inline-block;
  }

  .selected::after {
    position: absolute;
    content: "";
    width: calc(100% - 1em);
    height: 2px;
    background-color: rgb(255, 62, 0);
    display: block;
    bottom: -1px;
  }

  a {
    text-decoration: none;
    padding: 0.5em 0.5em;
    display: block;
  }

  .nav-right {
    display: flex;
    justify-content: flex-end;
  }
</style>

<nav>
  <ul>
    <li>
      <a class:selected={segment === undefined} href="." rel="prefetch">
        Morgan W
      </a>
    </li>
    <li>
      <a class:selected={segment === 'favs'} href="favs" rel="prefetch">favs</a>
    </li>
    <li>
      <a class:selected={segment === 'want'} href="want" rel="prefetch">want</a>
    </li>
    <div class="nav-right">
      <Socials scale=1.5/>
    </div>
    <!-- <li><a class:selected='{segment === "mdsvex"}' href='mdsvex' rel="prefetch">mdsvex</a></li> -->
  </ul>
</nav>
