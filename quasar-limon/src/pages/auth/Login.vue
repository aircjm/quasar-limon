<template>
  <q-layout>
    <q-page-container>
      <q-page class="flex bg-image flex-center">
        <q-card :style="$q.screen.lt.sm ? { width: '80%' } : { width: '45%' }">
          <q-card-section>
            <q-avatar size="100px" class="absolute-center shadow-10">
              <img src="../../statics/profile.svg"/>
            </q-avatar>
          </q-card-section>
          <q-card-section>
            <div class="text-center q-pt-lg">
              <div class="col text-h6 ellipsis">Log in</div>
            </div>
          </q-card-section>
          <q-card-section>
            <q-form class="q-gutter-md column">
              <q-input
                filled
                v-model="loginForm.username"
                label="Username"
                lazy-rules
              />
              <q-input
                type="password"
                filled
                v-model="loginForm.password"
                label="Password"
                lazy-rules
              />
              <q-field>
                <q-input
                  filled
                  v-model="loginForm.code"
                  label="code"
                  lazy-rules
                  style="max-width: 50%"
                />
                <q-img
                  :src="codeUrl"
                  @click="getCode"
                  style="height: 56px; max-width: 150px"
                />
              </q-field>
              <q-toggle
                label="记住密码"
                v-model="loginForm.rememberMe"
                checked-icon="check"
                color="green"
                unchecked-icon="clear"
              />
              <div>
                <q-btn
                  label="Login"
                  @click="onSubmit"
                  @keyup.enter="onSubmit"
                  type="button"
                  color="primary"
                />
              </div>
            </q-form>
          </q-card-section>
        </q-card>
      </q-page>
    </q-page-container>
  </q-layout>
</template>

<script lang="ts">
import {defineComponent, reactive} from 'vue';

export default defineComponent({
  setup() {
    const loginForm = reactive({
      username: '',
      password: '',
      rememberMe: false,
      code: '',
      uuid: ''
    })
    return [loginForm]
  }
});
</script>
