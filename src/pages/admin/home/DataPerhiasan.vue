<template>
  <q-page>
    <div class="q-pa-md">
      <q-table
        title="Treats"
        :data="data"
        :columns="columns"
        row-key="id"
        :filter="filter"
        :loading="loading"
      >

        <template v-slot:top>
          <q-btn color="teal" :disable="loading" label="Tambah Data Perhiasan" to="/admin/inputdataperhiasan" />
<!--          <q-btn class="q-ml-sm" color="primary" :disable="loading" label="Remove row" @click="removeRow" />-->
          <q-space />
          <q-input borderless dense debounce="300" color="primary" v-model="filter">
            <template v-slot:append>
              <q-icon name="search" />
            </template>
          </q-input>
        </template>

      </q-table>
    </div>
  </q-page>
</template>

<script>
export default {
  data () {
    return {
      loading: false,
      filter: '',
      rowCount: 10,
      columns: [
        {
          name: 'desc',
          required: true,
          label: 'Kode Perhiasan',
          align: 'left',
          field: row => row.kodeperhiasan,
          format: val => `${val}`,
          sortable: true
        },
        { name: 'jenisperhiasan', align: 'center', label: 'Jenis Perhiasan', field: 'jenisperhiasan', sortable: true },
        { name: 'kadarperhiasan', label: 'Kadar Perhiasan', align: 'center', field: 'kadarperhiasan', sortable: true },
        { name: 'beratperhiasan', label: 'Berat Perhiasan', align: 'center', field: 'beratperhiasan' },
        { name: 'hargaperhiasan', label: 'Harga Perhiasan', align: 'center', field: 'hargaperhiasan' }
      ],
      data: [
        {
          kodeperhiasan: 'KE001',
          jenisperhiasan: 'Kalung',
          kadarperhiasan: '24Karat',
          beratperhiasan: '20Gram',
          hargaperhiasan: 'Rp.180000000'
        },
        {
          kodeperhiasan: 'KE002',
          jenisperhiasan: 'Kalung',
          kadarperhiasan: '24Karat',
          beratperhiasan: '5Gram',
          hargaperhiasan: 'Rp.4500000'
        },
        {
          kodeperhiasan: 'CE001',
          jenisperhiasan: 'Cincin',
          kadarperhiasan: '24Karat',
          beratperhiasan: '5Gram',
          hargaperhiasan: 'Rp.45000000'
        },
        {
          kodeperhiasan: 'CE002',
          jenisperhiasan: 'Cincin',
          kadarperhiasan: '2Karat',
          beratperhiasan: '5Gram',
          hargaperhiasan: 'Rp.1800000'
        },
        {
          kodeperhiasan: 'GE001',
          jenisperhiasan: 'Gelang',
          kadarperhiasan: '24Karat',
          beratperhiasan: '10Gram',
          hargaperhiasan: 'Rp.90000000'
        },
        {
          kodeperhiasan: 'GE002',
          jenisperhiasan: 'Gelang',
          kadarperhiasan: '24Karat',
          beratperhiasan: '7Gram',
          hargaperhiasan: 'Rp.6300000'
        },
        {
          kodeperhiasan: 'CP001',
          jenisperhiasan: 'Cincin',
          kadarperhiasan: 'Perak',
          beratperhiasan: '1gram',
          hargaperhiasan: 'Rp.100000'
        },
        {
          kodeperhiasan: 'CP002',
          jenisperhiasan: 'Cincin',
          kadarperhiasan: 'Perak',
          beratperhiasan: '3Gram',
          hargaperhiasan: 'Rp.300000'
        },
        {
          kodeperhiasan: 'CP003',
          jenisperhiasan: 'Cincin',
          kadarperhiasan: 'Perak',
          beratperhiasan: '4Gram',
          hargaperhiasan: 'Rp.400000'
        },
        {
          kodeperhiasan: 'KP001',
          jenisperhiasan: 'Kalung',
          kadarperhiasan: 'Perak',
          beratperhiasan: '4Gram',
          hargaperhiasan: 'Rp.400000'
        },
        {
          kodeperhiasan: 'KP002',
          jenisperhiasan: 'Kalung',
          kadarperhiasan: 'Perak',
          beratperhiasan: '2Gram',
          hargaperhiasan: 'Rp.200000'
        },
        {
          kodeperhiasan: 'KP003',
          jenisperhiasan: 'Kalung',
          kadarperhiasan: 'Perak',
          beratperhiasan: '1Gram',
          hargaperhiasan: 'Rp.110000'
        },
        {
          kodeperhiasan: 'BR001',
          jenisperhiasan: 'Bross',
          kadarperhiasan: 'alumunium',
          beratperhiasan: '-',
          hargaperhiasan: 'Rp.80000'
        },
        {
          kodeperhiasan: 'BR002',
          jenisperhiasan: 'Bross',
          kadarperhiasan: 'alumunium',
          beratperhiasan: '-',
          hargaperhiasan: 'Rp.90000'
        },
        {
          kodeperhiasan: 'BR001',
          jenisperhiasan: 'Bross',
          kadarperhiasan: 'alumunium',
          beratperhiasan: '-',
          hargaperhiasan: 'Rp.100000'
        }
      ]
    }
  },

  methods: {
    // emulate fetching data from server
    addRow () {
      this.loading = true
      setTimeout(() => {
        const
          index = Math.floor(Math.random() * (this.data.length + 1)),
          row = this.original[Math.floor(Math.random() * this.original.length)]
        if (this.data.length === 0) {
          this.rowCount = 0
        }
        row.id = ++this.rowCount
        const addRow = { ...row } // extend({}, row, { name: `${row.name} (${row.__count})` })
        this.data = [...this.data.slice(0, index), addRow, ...this.data.slice(index)]
        this.loading = false
      }, 500)
    },

    removeRow () {
      this.loading = true
      setTimeout(() => {
        const index = Math.floor(Math.random() * this.data.length)
        this.data = [...this.data.slice(0, index), ...this.data.slice(index + 1)]
        this.loading = false
      }, 500)
    }
  }
}
</script>
