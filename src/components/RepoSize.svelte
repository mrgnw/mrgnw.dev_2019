<script>
  let site = "github.com";
  $: owner = "mrgnw";
  // $: repo = "svexiest";
  $: repo = "mzsh";
  $: url = `${site}/${owner}/${repo}`;
  $: switched = false;

  let size = 0;

  let gitPromise;

  function repoExists() {
    return true;
  }

  function unfocus() {
    console.log("unfocus");
  }

  function formatBytes(bytes, decimals = 1) {
    if (bytes === 0) return "0 Bytes";
    const k = 1024;
    const dm = decimals < 0 ? 0 : decimals;
    const sizes = ["Bytes", "KB", "MB", "GB", "TB", "PB", "EB", "ZB", "YB"];
    const i = Math.floor(Math.log(bytes) / Math.log(k));
    return parseFloat((bytes / Math.pow(k, i)).toFixed(dm)) + " " + sizes[i];
  }

  const loadGithubInfo = async () => {
    const response = await fetch(
      `https://api.github.com/repos/${owner}/${repo}`
    );
    if (response.status === 200) {
      return await response.json();
    } else {
      throw new Error(response.statusText);
    }
  };

  const handleClick = () => {
    gitPromise = loadGithubInfo();
  };

  function parsePaste() {
    let pasted_url = (event.clipboardData || window.clipboardData).getData(
      "text"
    );

    if (pasted_url.includes("github.com")) {
      owner = new URL(pasted_url).pathname.split("/")[1];
      repo = new URL(pasted_url).pathname.split("/")[2];
      console.log(`${owner}/${repo}`);
    }
  }

  function userPaste() {
    parsePaste();
    event.target.value = owner;
    event.preventDefault();
    handleClick();
  }
  function repoPaste() {
    parsePaste();
    event.target.value = repo;
    event.preventDefault();
    handleClick();
  }
</script>

<style>
  input {
    font-size: 1.2em;
    border: 0;
    outline: 0;
    background: transparent;
    min-width: 20px;
    max-width: 100px;
  }
  .multi-input {
    border-bottom: 1px solid black;
    max-width: 320px;
  }

  button {
    font-size: 2em;
    margin: 10px 0px 10px 0px;
    border-radius: 0.2em;
  }

  button:focus {
    outline: 0;
  }
</style>

<div>
  <slot />
</div>
<h1>Get repo size</h1>
<div>
  <div class="multi-input" on:focusout={unfocus}>
    <input on:paste={userPaste} bind:value={owner} />
    /
    <input on:paste={repoPaste} bind:value={repo} />
  </div>
  <!-- check url status / on unfocus  -->
  <a href={`https://${url}`} target="_blank">
    <label>{site}/</label>
    <b>{owner}/{repo}</b>
  </a>
</div>

{#await gitPromise}
  <p>...loading</p>
{:then apiResponse}
  <p>{apiResponse ? `${formatBytes(apiResponse.size)}` : ''}</p>
{:catch error}
  <p style="color: red">{error.message}</p>
{/await}

<div style="display: inline-block;">
  <button on:click={handleClick} type="submit">Get size</button>
  <!-- todo: save owner/repo for last request (don't update) -->
  <!-- <h2>{size} MB</h2> -->
</div>
