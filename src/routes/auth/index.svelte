<script lang="ts">
	import {Card, TextField, MaterialApp, Checkbox, Button} from 'svelte-materialify';
  
  //API fetch login
    let username = '';
    let password = '';
    async function login() {
      const response = await fetch('http://localhost:3001/signin',{
          method: 'POST',
          credentials: 'same-origin',
          body: JSON.stringify({ username, password }),
          headers: {
              'Content-Type': 'application/json'
          }
      })
      .then( response => {

        if ( response.status === 200) {
          window.location.href="/admin";
        }

        // what do you do with a non-redirect?

        }).catch((err) => {
        console.log(err);
      });
    }

  //Validasi form
 
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
        <form class="form">
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
          type="password"
          class="field"
          min="1"
          max="5"
          >Password</TextField>
          <div class="resetPass">
            <span>Forgot password?</span>
          </div>
        </form>
        <!-- <div class="checkbox">
          <Checkbox bind:group value="1">Remember me.</Checkbox>
        </div> -->
        <div class="submite" on:click={()=>login()}>
          <Button  touch>
           Sign in
          </Button>
        </div>
      </Card>
    </div>
</MaterialApp>
