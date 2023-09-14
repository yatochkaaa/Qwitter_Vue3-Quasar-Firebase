<template>
  <q-page>
    <div class="q-py-lg q-px-md row items-end q-col-gutter-md">
      <div class="col">
        <q-input
          class="new-qweet"
          v-model="newQweetContent"
          placeholder="What's happening?"
          maxlength="280"
          bottom-slots
          counter
          autogrow
        >
          <template v-slot:before>
            <q-avatar size="xl">
              <img src="../assets/okoloDnepra200x200.jpg" />
            </q-avatar>
          </template>
        </q-input>
      </div>
      <div class="col col-shrink">
        <q-btn
          class="q-mb-lg"
          unelevated
          rounded
          color="primary"
          label="Qweet"
          no-caps
          :disable="!newQweetContent"
        />
      </div>
    </div>

    <q-separator class="divider" size="10px" color="grey-2" />
  </q-page>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

interface State {
  newQweetContent: string;
}

export default defineComponent({
  name: 'HomePage',
  components: {},
  data(): State {
    return {
      newQweetContent: '',
    };
  },
});
</script>

<style lang="scss">
.new-qweet textarea {
  font-size: 19px;
  line-height: 1.4 !important;
}
.divider {
  border-top: 1px solid;
  border-bottom: 1px solid;
  border-color: $grey-4;
}
</style>
