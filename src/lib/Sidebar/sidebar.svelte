<script>
  import {page} from "$app/stores"
  import {
    List,
    Icon,
  } from 'svelte-materialify';
  import {
    mdiFolder,
    mdiAccountMultiple,
    mdiStar,
    mdiHistory,
    mdiCheckCircle,
    mdiUpload,
    mdiCloudUpload,
  } from '@mdi/js';
  import { writable } from 'svelte/store';
  const items = [
    { text: 'Dasboard', icon: mdiFolder, path: '/admin' },
    { text: 'Kelola Siswa', icon: mdiAccountMultiple, path:'/admin/siswa' },
    { text: 'Kelola Guru', icon: mdiStar,path:'/admin/guru' },
    { text: 'Kelola Kelas', icon: mdiHistory, path:'/admin/kelas' },
  ];
</script>

<main class="side">
  <List>
    <div class="title">
      <span>
        ONE_SKA
      </span>
    </div>
    <div class="content">
        {#each items as item}
            <div class="side" >
                <a class:active={$page.path === item.path} href={item.path}>
                  <div class="side-item">
                    <span><Icon path={item.icon} /></span>
                    <span>{item.text}</span>
                  </div>
                </a>
            </div>
        {/each}
    </div>
    </List>
</main>

<style lang="scss">
  .side{
    font-size: 16px;
      .title{
        padding: 20px 0px;
        border-bottom: 1px solid #083a45;
        span{
          padding-left: 20px;
        }
      }
      .content{
        .side{
          padding: 15px 20px;
          .side-item{
            display: flex;
            align-items: center;
            gap: 20px;
          }
          &:hover{
            background-color: rgba(255,255,255,0.10);;
          }
        }
        &::before{
          content: "";
          position: absolute;
          width: 199px;
          padding: 0;
          top: 128px;
          background:#083a45;
          height: 1px;
        }
        .active {
          color: #04b4cd;
          // font-weight: bold;
        }
      }
  }
</style>