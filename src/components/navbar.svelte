<script>
	import FormAdd from './addcontact.svelte';

  let navopen = false;
  let formadd = true;
</script>

<nav class="navbar is-dark">
  <div class="navbar-brand">
    <a href="/" class="navbar-item">BukuKontak</a>

    <button role="button" class="navbar-burger" aria-label="menu" aria-expanded="false" on:click="{() => navopen = !navopen}">
      <span aria-hidden="true" class="has-text-black"></span>
      <span aria-hidden="true" class="has-text-black"></span>
      <span aria-hidden="true" class="has-text-black"></span>
    </button>
  </div>

  <div class="navbar-menu {navopen? 'is-active' : ''}">
    <div class="navbar-end">
    {#if !formadd}
      <button class="button is-primary m-t-sm m-r-sm" on:click="{() => formadd = !formadd}">Tambah</button>
    {:else}
      <button class="button is-danger m-t-sm m-r-sm" on:click="{() => formadd = !formadd}">Batal</button>
    {/if}
    </div>
  </div>
</nav>

{#if formadd}
<FormAdd></FormAdd>
{/if}