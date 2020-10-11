<template>
  <div class="container">
    <InformationBar />
    <div class="resident-grid">
      <ResidentCard v-for="resident in residentArray" :key="resident.id" :resident="resident" />
    </div>
  </div>
</template>

<script>
export default {  
  data () {
    return {
      residentArray: [
        {
          id: 1,
          name: 'Jamie Oliver',
          suite: 119,
          floor: 'A1'
        },
        {
          id: 2,
          name: 'Jennifer Stark',
          suite: 111,
          floor: 'A1'
        },
        {
          id: 3,
          name: 'Natasha Romanoff',
          suite: 311,
          floor: 'C3'
        },
        {
          id: 5,
          name: 'Anduin Wrynn',
          suite: 201,
          floor: 'C2'
        },
        {
          id: 6,
          name: 'Bruce Banner',
          suite: 307,
          floor: 'C3'
        },
        {
          id: 21,
          name: 'Charles Chandler',
          suite: 119,
          floor: 'A1'
        },
        {
          id: 12,
          name: 'Christoph Nord',
          suite: 221,
          floor: 'B2'
        },
        {
          id: 13,
          name: 'Alfred Pennyworth',
          suite: 311,
          floor: 'C3'
        },
        {
          id: 14,
          name: 'Bolvar Fordragon',
          suite: 101,
          floor: 'A1'
        },
        {
          id: 15,
          name: 'Sylvanas Windrunner',
          suite: 212,
          floor: 'B2'
        },
      ]
    }
  }
}
</script>

<style lang="scss">
.container {
  margin: 0 auto;
  max-width: 90%;
}
.resident-grid {
  display:grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  grid-column-gap: 30px;
  grid-row-gap: 45px;
}
</style>
