<template>
  <section>
    <h1>Notes</h1>
    <p>Here are my notes</p>
    <ul>
      <li v-for="note in notes" :key="note.id">
        <h2>{{note.title}}</h2>
        <p>{{note.body}}</p>
        <div>
          <button @click="remove(note)">Remove</button>
        </div>
      </li>
    </ul>
    <div>
      <button @click="add()">Add</button>
    </div>
  </section>
</template>

<script>
export default {
  name: 'home',
  data () {
    return {
      nextNoteId: 3,
      notes: [
        {
          id: 1,
          title: 'note1',
          body: 'note body1'
        },
        {
          id: 2,
          title: 'note2',
          body: 'note body2'
        }
      ]
    }
  },
  methods: {
    add () {
      const id = this.nextNoteId++
      this.notes.push({
        id: id,
        title: 'new note ' + id,
        body: 'new note ' + id
      })
    },
    remove (note) {
      const index = this.notes.indexOf(note)
      this.notes.splice(index, 1)
    }
  }
}
</script>

<style scoped>
h2 {
  padding: 0;
}

ul {
  padding-left: 0;
  list-style: none;

}
li{
  margin-left: -.5em;
  margin-right: -.5em;
  border: 1px solid #ccc;
  padding:  .5em;
  box-shadow: 2px 2px 10px #ccc;
  border-radius: 5px;
}
</style>
