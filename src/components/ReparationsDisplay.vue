<template>
  <div class="hello">
    <div class="headers">
      <!-- <header v-for="field in Object.keys(records[0].fields)" :key="field">
        {{ field }}
      </header> -->
      <header>Location:</header>
      <header>Reparations to me means:</header>
            <header>The people to whom reparations must be made are:</header>
                        <header>My role in reparations is:</header>
                                          <header>The state's role in reparations is:</header>


    </div>
    <div class="entries">
      <div class="entry" v-for="record in reparations" v-bind:key="record.id">
        <div class="field left location">{{ record.fields["Location"] }}</div>
        <div class="field left">{{ record.fields["Reparations to me means:"] }}</div>
        <div class="field left">{{ record.fields["The people to whom reparations must be made are:"] }}</div>
        <div class="field left">{{ record.fields["My role in reparations is:"] }}</div>
        <div class="field left">{{ record.fields["The state's role in reparations is:"] }}</div>

      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ReparationsDisplay",
  data() {
    return {};
  },
  computed: {
    reparations() {
      return this.$store.state.reparations;
    }
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.headers {
  font-family: 'MuseoModerno', cursive;
  font-size: 1.3em;
  margin: 1vh 0;
  padding: 1vh 0;
  border-bottom: 1px solid;
  width: 100%;
  display: flex;
  flex-direction: row;
  align-items: flex-start;
  align-content: flex-start;
  justify-content: space-between;
  background-color: #FFDA4C;
}

header {
  height: auto;
  flex-basis: 40%;
  text-align: left;
  padding-left: .3em;
}

header:first-child {
  flex-basis: 13%;
}

a {
  color: inherit;
  text-decoration: none;
}

ul, p {
  padding: 0;
  margin: 0;
}

li {
  list-style: none;
}

.entries {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}

.entry {
  width: 100%;
  display: flex;
  flex-direction: row;
  align-items: flex-start;
  align-content: flex-start;
  justify-content: space-between;
  margin: 0.3vh 0.1vw;
}


.field {
  height: auto;
  flex-basis: 25%;
  overflow: scroll;
  padding: .4em;
}

.location {
  flex-basis:8%;
}


</style>
