/* eslint-disable vue/html-closing-bracket-newline */
<script setup lang="ts">
import Overview from '../components/Overview.vue'
import Hero1 from '~/components/Hero.vue'
const user = useUserStore()
const name = $ref(user.savedName)

const router = useRouter()
const go = () => {
  if (name)
    router.push(`/hi/${encodeURIComponent(name)}`)
}

const { t } = useI18n()
</script>

<template>
  <RouterLink
    class="icon-btn mx-2 mb-12 btn btn-primary"
    to="/nextgen"
    title="website reboot in Vue"
  >
    NextGen &rarr;
  </RouterLink>
  <main class="container mx-auto">
    <summit>
      <Hero />
      <Overview />
      <Sessions>
        <Session
          title="Jeff is a big doo doo head"
          name="Jeff Gibby"
          time="9 AM"
        />
        <Session
          title="I know what you did"
          name="Tom Piperson"
          time="10 AM"
        />
        <Session
          title="And why you did it"
          name="John Bowfinger"
          time="11 AM"
        />
      </Sessions>
    </summit>
  </main>

  <div class="hidden">
    <div class="grid grid-cols-3">
      <h1 class="bg-green-200 col-span-2">
        Hey Hey, were the mongeese
      </h1>
      <div
        i-carbon-campsite
        inline-block
      />
    </div>
    <p>
      <a
        rel="noreferrer"
        href="https://github.com/antfu/vitesse"
        target="_blank"
      >
        Vitesse
      </a>
    </p>
    <p>
      <em
        text-sm
        opacity-75
      >{{ t('intro.desc') }}</em>
    </p>

    <div py-4 />

    <input
      id="input"
      v-model="name"
      :placeholder="t('intro.whats-your-name')"
      :aria-label="t('intro.whats-your-name')"
      type="text"
      autocomplete="false"
      p="x4 y2"
      w="250px"
      text="center"
      bg="transparent"
      border="~ rounded gray-200 dark:gray-700"
      outline="none active:none"
      @keydown.enter="go"
    >
    <label
      class="hidden"
      for="input"
    >{{ t('intro.whats-your-name') }}</label>

    <div>
      <button
        btn
        m-3
        text-sm
        :disabled="!name"
        @click="go"
      >
        {{ t('button.go') }}
      </button>
    </div>
  </div>
</template>

<route lang="yaml">
meta:
  layout: home
</route>
