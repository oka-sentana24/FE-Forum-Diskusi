<script>
  import {
    List,
    ListItemGroup,
    NavigationDrawer,
    ListItem,
    Avatar,
    Icon,
    Divider,
  MaterialApp } from 'svelte-materialify';
  import {
    mdiFolder,
    mdiAccountMultiple,
    mdiStar,
    mdiHistory,
    mdiCheckCircle,
    mdiUpload,
    mdiCloudUpload,
  } from '@mdi/js';

  const items = [
    { text: 'Dasboard', icon: mdiFolder, href: '/admin' },
    { text: 'Kelola Siswa', icon: mdiAccountMultiple, href:'/admin/siswa' },
    { text: 'Starred', icon: mdiStar },
    { text: 'Recent', icon: mdiHistory },
    { text: 'Offline', icon: mdiCheckCircle },
    { text: 'Uploads', icon: mdiUpload },
    { text: 'Backups', icon: mdiCloudUpload },
  ];
  let active = false;
</script>

<NavigationDrawer>
  <div class="line w-full flex flex-cols-1 justify-center">
    <List nav dense>
      <div class="py-5">
        SMK NEGERI 1 GIANYAR
      </div>
      <div class="py-5">
        <ListItemGroup>
          {#each items as item}
            <ListItem>
              <span slot="prepend">
                <Icon path={item.icon} />
              </span>
              <a class="nav-list" href={item.href} >
                {item.text}
              </a>
            </ListItem>
          {/each}
        </ListItemGroup>
      </div>
      </List>
  </div>
</NavigationDrawer>