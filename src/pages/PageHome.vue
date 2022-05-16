<template>
  <q-page>
    <div class="q-py-lg q-px-md row items-end q-col-gutter-md">
      <div class="col">
        <q-input
          class="new-qweet"
          bottom-slots
          v-model="newQweetContent"
          placeholder="What's happening?"
          counter
          autogrow
          maxlength="280"
        >
          <template v-slot:before>
            <q-avatar size="xl">
              <img src="https://i.pravatar.cc/150?u=a042581f4e29026704d" />
            </q-avatar>
          </template>
        </q-input>
      </div>

      <div class="col col-shrink">
        <q-btn
          :disable="!newQweetContent"
          class="q-mb-lg"
          unelevated
          no-caps
          rounded
          color="primary"
          label="Qweet"
        />
      </div>
    </div>

    <q-separator class="divider" size="10px" color="grey-2" />

    <div class="q-pa-md q-gutter-md">
      <q-list>
        <q-item class="q-py-md">
          <q-item-section avatar top>
            <q-avatar size="xl">
              <img src="https://i.pravatar.cc/150?u=a042581f4e29026704d" />
            </q-avatar>
          </q-item-section>

          <q-item-section>
            <q-item-label class="text-subtitle1">
              <strong>User</strong>
              <span class="text-grey-7"> @user_handle</span>
            </q-item-label>
            <q-item-label class="qweet-content text-body1">
              Lorem ipsum dolor, sit amet consectetur adipisicing elit.
              Architecto, rem! Incidunt eos dolor adipisci natus quod assumenda
              itaque architecto ut corporis numquam consequuntur, repellat iste.
              Quibusdam, saepe?
            </q-item-label>
            <div class="qweet-icons row justify-between q-mt-sm">
              <q-btn flat round color="grey" icon="far fa-comment" size="sm" />
              <q-btn flat round color="grey" icon="fas fa-retweet" size="sm" />
              <q-btn flat round color="grey" icon="far fa-heart" size="sm" />
              <q-btn flat round color="grey" icon="fas fa-trash" size="sm" />
            </div>
          </q-item-section>

          <q-item-section side top> 1 min ago </q-item-section>
        </q-item>
      </q-list>
    </div>
  </q-page>
</template>

<script>
import { defineComponent } from "vue";

export default defineComponent({
  name: "PageHome",
  data() {
    return {
      newQweetContent: "",
    };
  },
});
</script>

<style lang="sass">
.new-qweet
  textarea
    font-size: 19px
    line-height: 1.4 !important
.divider
  border-top: 1px solid
  border-bottom: 1px solid
  border-color: $grey-4
.qweet:not(:first-child)
  border-top: 1px solid rgba(0, 0, 0, 0.12)
.qweet-content
  white-space: pre-line
.qweet-icons
  margin-left: -5px
</style>
