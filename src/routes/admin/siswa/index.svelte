<script>
  // @ts-nocheck
    import {
      DataTable,
      DataTableHead,
      DataTableRow,
      DataTableCell,
      DataTableBody,
      Button,
      Row, Col, Select,Checkbox
   } from 'svelte-materialify';
   import Link from "svelte-link";
    let checked = false;
    let group = [1,2,3,4,5]

  const items = [
    { name: 'Delete', value: 'Delete' },
  ];

  let columns = ["Nisn", "Nama", "Jurusan", "Kelas", "Alamat", "Jenis Kelamin", "Tempat lahir", "Agama", "No tlp", "Email"]
	let data = [
    ["170030299", "john@example.com", "(353) 01 222 3333","john@example.com", "(353) 01 222 3333","john@example.com", "(353) 01 222 3333","(353) 01 222 3333","john@example.com", "(353) 01 222 3333"],
    ["170030299", "john@example.com", "(353) 01 222 3333","john@example.com", "(353) 01 222 3333","john@example.com", "(353) 01 222 3333","(353) 01 222 3333","john@example.com", "(353) 01 222 3333"],
    ["170030299", "john@example.com", "(353) 01 222 3333","john@example.com", "(353) 01 222 3333","john@example.com", "(353) 01 222 3333","(353) 01 222 3333","john@example.com", "(353) 01 222 3333"],
    ["170030299", "john@example.com", "(353) 01 222 3333","john@example.com", "(353) 01 222 3333","john@example.com", "(353) 01 222 3333","(353) 01 222 3333","john@example.com", "(353) 01 222 3333"],
    ["170030299", "john@example.com", "(353) 01 222 3333","john@example.com", "(353) 01 222 3333","john@example.com", "(353) 01 222 3333","(353) 01 222 3333","john@example.com", "(353) 01 222 3333"],
    
  ]

  //Checkall Checkbox


  </script>

  <div class="main-siswa">
    <div class="flex flex-cols-2 justify-between py-5 items-center">
      <div class="filter">
        <Row>
          <Col>
            <Select solo items={items} placeholder="Filter"/>
          </Col>
        </Row>
      </div>
      <div class="create">
        <Button><a href="/admin/siswa/create">
          New siswa
        </a></Button>
      </div>
    </div>
    <div class="main-tabel">  
        <DataTable>
          <DataTableHead>
            <DataTableRow>
              {#each columns as column}
              <DataTableCell>{column}</DataTableCell>
              {/each}
            </DataTableRow>
          </DataTableHead>
          <DataTableBody>
            {#each data as row}
            <DataTableRow>
                {#each row as cell}
                  <DataTableCell>
                    {cell}
                  </DataTableCell>
                  {/each}
            </DataTableRow>
            {/each}
          </DataTableBody>
        </DataTable>
    </div>
  </div>