<script>
  import { Breadcrumbs,List, ListGroup, ListItem, Avatar,Icon, Divider, Button} from 'svelte-materialify';
  import { mdiAlertCircle } from '@mdi/js';
  import { mdiBellBadge } from '@mdi/js';
  import { mdiSearchWeb } from '@mdi/js';
  import { mdiMagnify } from '@mdi/js';
  import { mdiClose } from '@mdi/js';
  import { createEventDispatcher } from 'svelte';
  import { mdiHome, mdiCog, mdiChevronUp } from '@mdi/js';
  import { mdiLogout } from '@mdi/js';
  import { mdiAccountCircleOutline } from '@mdi/js';
  import Breadcrumb from '$lib/BreadCrumb.svelte';
  import { page } from '$app/stores';

  let active = false;
  const items = [
    { text: 'Dashboard', href: '/components/breadcrumbs/' },
    { text: 'Link 1', href: '/components/breadcrumbs/' },
    { text: 'Link 2', disabled: true },
  ];
  let isOpenSearch = false;
  let isOpenProfile = false;
  let dispatch = createEventDispatcher();

  export function show() {
    isOpenProfile = !isOpenProfile;
      dispatch('show', isOpenProfile);
  }
</script>
  <div  class="flex flex-col-2 gap-4 justify-between w-full">
    <div class="breadcrumb">
      <!-- <Breadcrumbs {items} let:item>
        {#if item.href}
          <a class="s-breadcrumb-item" href={item.href} class:disabled={item.disabled}>
            {item.text.toUpperCase()}
          </a>
        {:else}
          <span class="s-breadcrumb-item" class:disabled={item.disabled}>
            {item.text.toUpperCase()}
          </span>
        {/if}
      </Breadcrumbs> -->
      <Breadcrumb path={$page.path} />
    </div>
    <div class="contents">
      <div class="flex flex-cols-4 gap-4 justify-center items-center pr-5">
        <div class="search" on:click={()=> isOpenSearch = true}>
         <Icon path={mdiSearchWeb} />
        </div>
        <div class="message">
          <Icon path={mdiAlertCircle} />
        </div>
        <div class="nontifikasi">
          <Icon path={mdiBellBadge} />
        </div>
        <div class="profile cursor-pointer" on:click={show}>
          <Avatar size="36px" class="red white-text"><b>MS</b></Avatar>
        </div>
      </div>
    </div>
  </div>
    {#if isOpenSearch}
    <div class="main-search w-full top-0 absolute p-3">
        <div class="container mx-3 md:container md:w-3/4 lg:container lg:w-full">
          <div class="flex flex-cols-2 items-center justify-between gap-3 w-full">
            <div class="flex flex-cols-2 gap-3 w-full">
              <span>
                <Icon path={mdiMagnify}/>
              </span>
             <input type="text" placeholder="Search from page" class="w-full border-0">
            </div>
            <div on:click="{()=> isOpenSearch = false}">
              <Icon path={mdiClose}/>
            </div>
          </div>
        </div>
      </div>
    {/if}
    {#if isOpenProfile}
    <div class="main-profle">
      <div class="d-flex justify-end">
        <div class="list">
          <ListItem>
            <div slot="prepend">
              <Avatar><img src="//picsum.photos/100?random=1" alt="Avatar" /></Avatar>
            </div>
            Study Group
            <span slot="subtitle"> <b>John Doe</b> - This is my message </span>
          </ListItem>
          <hr class="line"/>
          <div class="setting">
            <div class="flex flex-cols-2 w-full gap-3">
              <span><Icon path={mdiAccountCircleOutline}/></span>
              <span>Profile</span>
            </div>
          </div>
          <div class="setting">
            <div class="flex flex-cols-2 w-full gap-3">
              <span><Icon path={mdiCog} /></span>
              <span>Profile</span>
            </div>
          </div>
          <hr class="line"/>
          <ListItem>
            <div class="logout flex flex-cols-2 w-full gap-3 items-center">
                <span><Icon path={mdiLogout} /></span>
                <span>Sign out</span>
            </div>
          </ListItem>
        </div>
      </div>
    </div>
    {/if}

  <style lang="scss">
    .main-search{
      width: 86%;
      background: #1e293b;
    }
    .main-profle{
      .list{
        width: 200px;
        height: fit-content;
        background: #083a45 !important;
        border-radius: 5px;
        position: absolute;
        margin-right: 19px;
        color: white;
      }
      .setting{
        padding: 16px;
      }
      .logout{
        height: 3vh;
      }
      .line {
          border-color: #04b4cd !important;
          opacity: 0.3 !important;
      } 
    }
  </style>
  