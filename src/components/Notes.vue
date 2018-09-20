<template>
  <section>
    <h1>Notes</h1>
    <p>Here are my notes</p>
    <ul>
      <li v-for="note in notes" :key="note.id">
        <div v-if="!note.isEditing">
          <h2>{{note.title}}</h2>
          <p>{{note.body}}</p>
          <div>
            <button @click="edit(note)">Edit</button>
          </div>
        </div>
        <div v-if="note.isEditing">
          <fieldset>
            <label>Title</label>
            <input type="text" v-model="note.title">
          </fieldset>
          <fieldset>
            <label>Body</label>
            <textarea type="text" v-model="note.body" />
          </fieldset>
          <div>
            <button @click="remove(note)">Remove</button>
            <button @click="cancelEdit(note)">Cancel</button>
          </div>
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
    },
    edit (note) {
      note.isEditing = true
      const index = this.notes.indexOf(note)
      this.notes.splice(index, 1, note)
    },
    cancelEdit (note) {
      note.isEditing = false
      const index = this.notes.indexOf(note)
      this.notes.splice(index, 1, note)
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
