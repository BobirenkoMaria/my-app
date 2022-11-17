<template>
  <main class="list">
    <ListComponent
      v-for="elem in todo_list"
      :key="elem"
      :id="elem.id"
      :name="elem.name"
      :description="elem.description"
      @deleteElement="(id) => deleteElement(id)"
    >
    </ListComponent>
  </main>
  <footerComponent></footerComponent>
</template>

<script>
import FooterComponent from './components/footerComponent.vue';
import ListComponent from './components/listComponent.vue';

export default {
  name: 'App',
  components: {
    ListComponent,
    FooterComponent
  },
  data() {
        return {
            todo_list: [
                {
                    "id": 1,
                    "name": "Task-1",
                    "description": "Титаническая работа! Мало того, что на русский перевели, так еще и спеть смогли!  Очень тяжелая песня! Учитывая наши фонетические обороты, запятые, ударения... Оч круто! Спасибо!"
                },
                {
                    "id": 2,
                    "name": "Task-2",
                    "description": "Then, when we listen to the event in the parent, we can use an inline arrow function as the listener, which allows us to access the event argument"
                },
                {
                    "id": 3,
                    "name": "Task-3",
                    "description": "Should do"
                },
            ]
        };
    },
  methods: {
    deleteElement(id){
      this.todo_list.forEach(function(element) {
        if(element.id == id) {
          alert(id)
          delete this.todo_list[id]
        }
      });

    }
  }
}
</script>

<style>
.list {
    margin: 10px;
    font-size: 50px;
}
</style>
