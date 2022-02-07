<script>
  // @ts-nocheck
    import {
      DataTable,
      DataTableHead,
      DataTableRow,
      DataTableCell,
      DataTableBody,
    MaterialApp } from 'svelte-materialify';
    import {Button} from 'svelte-materialify';
    import { Row, Col, Select} from 'svelte-materialify';
    import { Checkbox} from 'svelte-materialify';

  const items = [
    { name: 'Delete', value: 'Delete' },
  ];
  let group = ['2'];
  let columns = ["Name", "Email", "Phone Number"]
	let data = [
    ["John", "john@example.com", "(353) 01 222 3333"],
    ["Mark", "mark@gmail.com", "(01) 22 888 4444"],
    ["Eoin", "eoin@gmail.com", "0097 22 654 00033"],
    ["Sarah", "sarahcdd@gmail.com", "+322 876 1233"],
    ["Afshin", "afshin@mail.com", "(353) 22 87 8356"]
  ]
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
        <Button depressed class="primary-color">Primary</Button>
      </div>
    </div>
    <div class="main-tabel">  
        <DataTable>
          <DataTableHead>
            <DataTableRow>
              <DataTableCell>
                <Checkbox bind:group value="1"/>
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
                <Checkbox bind:group value="2"/>
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