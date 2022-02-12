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
    let checked = false;
    let group = [1,2,3,4,5]

  const items = [
    { name: 'Delete', value: 'Delete' },
  ];

  let columns = ["Nisn", "Nama", "Jurusan", "Kelas", "Alamat", "Jenis Kelamin", "Tempat lahir", "Agama", "No tlp", "Email", "Kewarganegaraan", "Kecamatan", "Kabupaten"]
	let data = [
    ["John", "john@example.com", "(353) 01 222 3333"],
    ["Mark", "mark@gmail.com", "(01) 22 888 4444"],
    ["Eoin", "eoin@gmail.com", "0097 22 654 00033"],
    ["Sarah", "sarahcdd@gmail.com", "+322 876 1233"],
    ["Afshin", "afshin@mail.com", "(353) 22 87 8356"],
    
  ]

  //Checkall Checkbox


  </script>

  <div class="main-siswa">
    <div class="flex flex-cols-2 justify-between py-5 items-center">
      <div class="filter">
        <Row>
          <Col>
            <Select solo items={items} placeholder="Bulk Action"/>
          </Col>
        </Row>
      </div>
      <div class="create">
        <Button>New siswa</Button>
      </div>
    </div>
    <div class="main-tabel">  
        <DataTable>
          <DataTableHead>
            <DataTableRow>
              <DataTableCell>
                <Checkbox bind:group value={data}/>
              </DataTableCell>
              {#each columns as column}
              <DataTableCell>{column}</DataTableCell>
              {/each}
            </DataTableRow>
          </DataTableHead>
          <DataTableBody>
            {#each data as row}
            <DataTableRow>
              <DataTableCell>
                <Checkbox bind:group value={data}/>
              </DataTableCell>
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