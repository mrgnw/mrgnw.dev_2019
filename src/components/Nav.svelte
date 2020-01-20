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

  /* .nav-right {
    display: flex;
    justify-content: flex-end;
  } */
</style>

<nav>
  <ul class="nav-left">
    <li>
      <a class:selected={segment === undefined} href="." rel="prefetch">
        Morgan W
      </a>
    </li>
    <li>
      <a class:selected={segment === 'favs'} href="favs" rel="prefetch">favs</a>
    </li>
    <!-- <li><a class:selected='{segment === "mdsvex"}' href='mdsvex' rel="prefetch">mdsvex</a></li> -->
    <!-- <li><a class:selected='{segment === "about"}' href='about'>about</a></li> -->
    <!-- <li><Icon
			path="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12"
		/></li> -->
    <!-- for the blog link, we're using rel=prefetch so that Sapper prefetches
		     the blog data when we hover over the link or tap it on a touchscreen -->
    <!-- <li><a rel=prefetch class:selected='{segment === "blog"}' href='blog'>blog</a></li> -->
  </ul>
  <!-- <div class="nav-right"> -->
  <!-- <Socials /> -->
  <!-- </div> -->
</nav>
