<template xmlns:v-slot="http://www.w3.org/1999/XSL/Transform">
  <q-page padding class="items-center-justify-center bg-grey-3">
    <q-card flat class="bg-white q-pa-md">
      <span class="text-h5 text-weight-light q-pa-md">
        <span class="text-blue-grey-14">Tambah Data Perhiasan</span>
      </span>
      <div class="q-pa-md">
        <q-form
          class="q-gutter-md"
        >

          <q-input
            label="Kode Perhiasan"
            lazy-rules
            color="teal"
            v-model="kodeperhiasan"
            :rules="[
           val => val !== null && val !== '' || 'Kode Perhiasan Dibutuhkan'
           ]">
            <template v-slot:append>
              <q-icon name="dns"/>
            </template>
          </q-input>

          <q-input
            label="Jenis Perhiasan"
            lazy-rules
            color="teal"
            v-model="jenisperhiasan"
            :rules="[
           val => val !== null && val !== '' || 'Jenis Perhiasan Dibutuhkan'
           ]">
            <template v-slot:append>
              <q-icon name="title"/>
            </template>
          </q-input>
          <q-input
            label="Kadar Perhiasan"
            lazy-rules
            color="teal"
            v-model="kadarperhiasan"
            :rules="[
           val => val !== null && val !== '' || 'Kadar Perhiasan Dibutuhkan'
           ]">
            <template v-slot:append>
              <q-icon name="local_offer"/>
            </template>
          </q-input>
          <q-input
            label="Berat Perhiasan"
            lazy-rules
            color="teal"
            v-model="beratperhiasan"
            :rules="[
           val => val !== null && val !== '' || 'Berat Perhiasan Dibutuhkan'
           ]">
            <template v-slot:append>
              <q-icon name="gavel"/>
            </template>
          </q-input>
          <q-input
            label="Harga Perhiasan"
            lazy-rules
            color="teal"
            v-model="hargaperhiasan"
            :rules="[
           val => val !== null && val !== '' || 'Harga Perhiasan Dibutuhkan'
           ]">
            <template v-slot:append>
              <q-icon name="attach_money"/>
            </template>
          </q-input>
          <div>
            <q-btn
              unelevated
              icon="add"
              label="Tambah Data Perhiasan"
              style="height: 50px"
              color="teal-6"/>
          </div>
        </q-form>
      </div>
    </q-card>
  </q-page>
</template>

<script>
export default {
  data () {
    return {
      kodeperhiasan: null,
      jenisperhiasan: null,
      kadarperhiasan: null,
      beratperhiasan: null,
      hargaperhiasan: null
    }
  }
}
</script>

<style scoped>

</style>
