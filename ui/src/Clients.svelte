

<script>
    import SuDisclaimer from "./SuDisclaimer.svelte";
  import { getContext } from 'svelte';
  import Fab, {Label, Icon} from '@smui/fab';
  import { onMount } from 'svelte';
	import Client from './Client.svelte';
  const { open } = getContext('simple-modal');

  export let user;

  let clientsUrl = "/api/v1/users/" + user + "/clients";
  let clients = [];

  async function getClients() {
    const res = await fetch(clientsUrl);
		clients = Object.entries(await res.json());
    console.log("Fetched clients", clients);
  }

  async function handleNewClick(event) {
    const res = await fetch(clientsUrl, {
      method: "POST",
    })
      .then(response => {
        return response.json()
    })
    .then(data => {
      if (typeof data.Error != "undefined") {
          console.log(data.Error);
          alert(data.Error);
    } else {
        console.log("New client added", data);
    }
  });
    await getClients();
  }


  onMount(() => {
    getClients();
    showDisclaimer();
    });

  const showDisclaimer = () => {
    open(SuDisclaimer, { message: "Viktigt meddelande" });
  };
</script>

<style>
.newClient {
  float: right;
}

h2 small {
  display: block;
  clear: left;
  color: #ccc;
}


.content {}

.row {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  width: 100%;
}

.col {
  display: flex;
  flex-direction: column;
  flex-basis: 100%;
  flex: 1;
  margin-left: 2em;
}

.help {
flex-basis: 10%;
}

h2 {
margin: 0;
padding: 0;
}
</style>

<div class="content">
  <div class="row">
    <div class="col">
      <h2 class="mdc-typography--headline2">My VPN Clients<small class="mdc-typography--headline5">({user})</small></h2>
    </div>
    <div class="col help">
      <h3>Instructions</h3>
      <ol>
        <li><a href="https://serviceportalen.su.se/sv-se/article/1319269" target="_blank">Install WireGuard (opens in a new tab)</a></li>
        <li>Create the configuration by hitting the button in the bottom right hand corner</li>
        <li>Download the configuration (or use the QR-code on a mobile device)</li>
        <li>Start Wireguard, add the configuration and activate the tunnel</li>
      </ol>
    <div class="col help">
        Make sure to create a config for each device (computer, phone, etc). Do not reuse configuration for multiple devices.<br/>
    </div>
    </div>
  </div>

</div>

      {#each clients as dev}
        <Client user={user} client={dev}/>
      {/each}

      <div class="newClient">
        <Fab color="primary" on:click={handleNewClick}><Icon class="material-icons">add</Icon></Fab>
      </div>


