<script context="module">
  import {TextField} from 'svelte-materialify';
  export const value = "";
  export const label = "";
  export const name = "";
  export const type = "";
  export const pending = false;
  export const errors = {};
  export const onInput = () => {};

  const messages = errors[name] || [];
</script>

  <!-- <input type="text" {name} bind:value {...$$props} on:input={onInput} /> -->
  <!-- <TextField
      filled
      class="field"
      type={type} name={name} bind:value {...$$props} on:input={onInput
    >{label}
  </TextField> -->
  <TextField filled class="field" type={type}>
    <span>{label}</span>
   </TextField>
  {#if messages.length}
      <span class="col-xs-8 error-container">{messages[0]}</span>
  {/if}