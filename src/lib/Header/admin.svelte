<script>
  import { Breadcrumbs, MaterialApp } from 'svelte-materialify';
  import { Avatar, Icon} from 'svelte-materialify';
  import { mdiAlertCircle } from '@mdi/js';
  import { mdiBellBadge } from '@mdi/js';
  import { mdiSearchWeb } from '@mdi/js';

  const items = [
    { text: 'Dashboard', href: '/components/breadcrumbs/' },
    { text: 'Link 1', href: '/components/breadcrumbs/' },
    { text: 'Link 2', disabled: true },
  ];
</script>
  <div  class="flex flex-col-2 gap-4 justify-between w-full">
    <div class="breadcrumb">
      <Breadcrumbs {items} let:item>
        {#if item.href}
          <a class="s-breadcrumb-item" href={item.href} class:disabled={item.disabled}>
            {item.text.toUpperCase()}
          </a>
        {:else}
          <span class="s-breadcrumb-item" class:disabled={item.disabled}>
            {item.text.toUpperCase()}
          </span>
        {/if}
      </Breadcrumbs>
    </div>
    <div class="contents">
      <div class="flex flex-cols-4 gap-4 justify-center items-center pr-5">
        <div class="search">
         <Icon path={mdiSearchWeb} />
        </div>
        <div class="message">
          <Icon path={mdiAlertCircle} />
        </div>
        <div class="nontifikasi">
          <Icon path={mdiBellBadge} />
        </div>
        <div class="profile">
          <Avatar size="36px" class="red white-text"><b>MS</b></Avatar>
        </div>
      </div>
    </div>
  </div>