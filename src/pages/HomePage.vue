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

    <q-list>
      <q-item class="q-py-md">
        <q-item-section avatar top>
          <q-avatar>
            <img src="../assets/okoloDnepra200x200.jpg" />
          </q-avatar>
        </q-item-section>

        <q-item-section>
          <q-item-label class="text-subtitle1">
            <strong>Volodymyr Taranin</strong>
            <span class="text-grey-7"> @volodymyr_taranin </span>
          </q-item-label>
          <q-item-label class="text-body1">
            Lorem ipsum, dolor sit amet consectetur adipisicing elit. Fugiat
            enim illo hic quod molestias omnis optio voluptate, vitae alias ea
            recusandae autem molestiae praesentium, totam possimus nulla
            doloremque nobis ab.
          </q-item-label>
          <div class="qweet-icons row justify-between q-mt-sm">
            <q-btn
              flat
              round
              color="grey"
              icon="fa-regular fa-comment"
              size="sm"
            />
            <q-btn
              flat
              round
              color="grey"
              icon="fa-solid fa-retweet"
              size="sm"
            />
            <q-btn
              flat
              round
              color="grey"
              icon="fa-regular fa-heart"
              size="sm"
            />
            <q-btn flat round color="grey" icon="fa-solid fa-trash" size="sm" />
          </div>
        </q-item-section>

        <q-item-section side top> 1 min ago </q-item-section>
      </q-item>
    </q-list>
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
.qweet-icons {
  margin-left: -5px;
}
</style>
