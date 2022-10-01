<script>
  import { username, user } from './user';

  function signout() {
    user.leave();
    username.set('');
  }
</script>

<header>
<!-- svelte-ignore a11y-missing-content -->
<h1 class="logo"></h1>
  {#if $username}
    <div class="user-bio">
      
      <span>Hello, <strong>{$username}</strong></span>
      <img src={`https://avatars.dicebear.com/api/initials/${$username}.svg`} alt="avatar" /> 
    </div>

    <button class="signout-button" on:click={signout}></button>

    {:else}

      <h1>💬</h1>
  {/if}
</header>