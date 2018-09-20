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
            <button @click="edit(note)"><i class="far fa-edit"></i> Edit</button>
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
            <button @click="done(note)"><i class="far fa-check-circle"></i> Done</button>
            <button @click="remove(note)"><i class="far fa-trash-alt"></i> Remove</button>
          </div>
        </div>
      </li>
    </ul>
    <div>
      <button @click="add()"><i class="far fa-plus-square"></i> Add</button>
    </div>
  </section>
</template>

<script>
export default {
  name: 'home',
  data () {
    return {
      nextNoteId: 1,
      notes: []
    }
  },
  mounted () {
    this.notes = JSON.parse(localStorage.getItem('notes')) || []
    this.nextNoteId = JSON.parse(localStorage.getItem('nextNoteId')) || 1
  },
  methods: {
    add () {
      const id = this.nextNoteId++
      this.notes.push({
        id: id,
        title: 'new note ' + id,
        body: 'new note ' + id
      })
      this.save()
    },
    remove (note) {
      const index = this.notes.indexOf(note)
      this.notes.splice(index, 1)
      this.save()
    },
    edit (note) {
      note.isEditing = true
      const index = this.notes.indexOf(note)
      this.notes.splice(index, 1, note)
    },
    done (note) {
      note.isEditing = false
      const index = this.notes.indexOf(note)
      this.notes.splice(index, 1, note)
      this.save()
    },
    save () {
      localStorage.setItem('notes', JSON.stringify(this.notes))
      localStorage.setItem('nextNoteId', JSON.stringify(this.nextNoteId))
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
