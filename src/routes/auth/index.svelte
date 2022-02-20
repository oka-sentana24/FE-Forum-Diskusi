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
  const validasiusername = [
    (v) => !!v || 'Required',
    (v) => v.length <= 25 || 'Max 25 characters',
    (v) => {
      const pattern = /[0-9][A-Za-z0-9 -]*$/;
      return pattern.test(v) || 'INVALID Nip/Nisn.';
    },
  ];
  const validasipassword = [
    (v) => !!v || 'Required',
    (v) => {
      const pattern = /^[a-zA-Z0-9]+$/;
      return pattern.test(v) || 'INVALID Password.';
    },
  ];
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
            type="username"
            class="field"
            rules={validasiusername}
            bind:value={username}
          >Nisn / Nip</TextField>
          <TextField
          filled
          type="password"
          class="field"
          rules={validasipassword}
          bind:value={password}
          >Password</TextField>
          <div class="resetPass">
            <span>Forgot password?</span>
          </div>
        </form>
        <div class="checkbox">
          <Checkbox checked={false}>Remember me.</Checkbox>
        </div>
        <div class="submite" on:click={()=>login()}>
          <Button  touch>
           Sign in
          </Button>
        </div>
      </Card>
    </div>
</MaterialApp>
