<script setup>
import Title from './Title.vue'
import FirstParagraph from './FirstParagraph.vue'
import SecondParagraph from './SecondParagraph.vue'
import ThirdParagraph from './ThirdParagraph.vue'

const props = defineProps({
  personInfos: Object,
})
</script>

<template>
  <section>
    <img
      src="https://res.cloudinary.com/lereacteur-apollo/image/upload/v1704967000/RNCP31114/cours-vue/exo-sem-1/mystery-person_bueack.jpg"
    />
    <div>
      <Title
        :firstname="personInfos.firstname"
        :lastname="personInfos.lastname"
        :gender="personInfos.gender"
      />
      <FirstParagraph :gender="personInfos.gender" :age="personInfos.age" :job="personInfos.job" />
      <SecondParagraph :firstname="personInfos.firstname" :hobbies="personInfos.hobbies" />
      <ThirdParagraph :gender="personInfos.gender" :pet="personInfos.pet" />
    </div>
    <font-awesome-icon :icon="['fas', 'heart']" />
  </section>
</template>

<style scoped>
section {
  display: flex;
  flex-direction: column;
  background-color: lightgray;
  flex: 1;
  padding-left: 10px;
  padding-right: 10px;
  padding-top: 10px;
  border-radius: 10px;
  box-shadow: 0 0 7px v-bind('personInfos.favoriteColor');
}

img {
  width: 100%;
  object-fit: cover;
  object-position: top;
}

svg {
  color: gray;
  align-self: flex-end;
  margin-bottom: 10px;
}

/*--------Media Query--------------*/

@media (max-width: 1250px) {
  section {
    flex: none;
    width: 275px;
  }
}
</style>
