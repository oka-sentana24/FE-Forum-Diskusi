<script lang="ts" context="module">
  export const ssr = false;
	import {Card, TextField, MaterialApp, Checkbox, Button} from 'svelte-materialify';
  import { API } from '../../api/Api';
	let username = '';
	let password = '';
	let group = ['2'];

  
  const getPokemonList = async () => {
    try {
      const response = await API.post("signin",{username,password});
      console.log(response)
      return response.results;
    } catch (error) {
      console.error(error);
    }
  // import { onMount } from "svelte";
  // const endpoint = "https://jsonplaceholder.typicode.com/posts";
  // let posts = [];

  // onMount(async function () {
  //   const response = await fetch(endpoint);
  //   const data = await response.json();
  //   console.log(data);
  // });
};
</script>
<MaterialApp>
    <div class="main-auth-login">
      <Card class="card">
        <div class="content-form">
          <div class="title">
            <span>Signin</span>
          </div>
          <span class="description">
            Belum memiliki akun? <span class="sub">hubungi pihak sekolah</span>.
          </span>
        </div>
        <form action="" class="form">
          <TextField
           filled
            bind:value={username}
            type="number"
            class="field"
            min="1"
            max="5"
          >Nisn / Nip</TextField>
          <TextField
          filled
          bind:value={password}
          type="text"
          class="field"
          min="1"
          max="5"
          >Password</TextField>
          <div class="resetPass">
            <span>Forgot password?</span>
          </div>
        </form>
        <div class="checkbox">
          <Checkbox bind:group value="1">Remember me.</Checkbox>
        </div>
        <div class="submite">
          <Button on:click={() => getPokemonList()} touch>
           Sign in
          </Button>
        </div>
      </Card>
    </div>
</MaterialApp>
