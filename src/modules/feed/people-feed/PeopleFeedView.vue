<script setup lang="ts">
import PersonCard from "@/modules/feed/people-feed/components/PersonCard/PersonCard.vue";
import { feedPeople } from "@/modules/feed/people-feed/composable/fetchFeedPeople";
import { openPersonModal } from "@/common/composables/personModalState";
</script>

<template>
  <div class="feed">
    <PersonCard
      v-for="person in feedPeople"
      :name="person.name"
      :occupation="person.occupation"
      :img-url="person.imgUrl"
      :interactions-count="person.interactionsCount"
      @click="openPersonModal"
    />
  </div>
</template>

<style scoped>
.feed {
  width: 100%;
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
}

.ant-input {
  margin: 20px;
  background: #ccc;
}
</style>
