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
  <main class="container mx-auto">
    <div class="flex w-full">
      <div class="grid h-20 flex-grow card bg-base-300 rounded-box place-items-center">
        content
      </div>
      <div class="divider divider-horizontal">
        OR
      </div>
      <div class="grid h-20 flex-grow card bg-base-300 rounded-box place-items-center">
        content
      </div>
    </div>
  </main>

  <section class="bg-indigo-50 py-12">
    <div class="container mx-auto px-[2vw] ">
      <div class="flex gap-x-4 flex-col md:flex-row w-full">
        <div class="grid h-auto md:w-2/3 flex-grow card  place-items-center space-y-4">
          <h1 class="text-2xl text-center text-orange-600 font-bold">
            MetaStock - A Global Leader in Market Analysis Tools
          </h1>
          <div class="content w-[clamp(30ch,_100%,_65ch)]">
            <p>
              MetaStock has been providing award-winning charting and analysis tools for the self-directed trader for
              over 30 years. Capitalizing on technical analysis, our line of trading software and market data are
              designed for active traders of all levels so they can backtest, scan and analyze the markets with
              confidence.
            </p>
            <p>
              The result is buy and sell signals you can count on. We have options for day traders, swing traders and
              EOD traders to trade stocks, options, futures, FOREX and more. Try MetaStock and we are confident you’ll
              agree that it’s the best charting software available to the private trader.
            </p>
            <div
              class="buttons flex flex-col lg:flex-row w-4/5 mx-auto mt-4  text-center space-y-2 lg:space-y-0 lg:space-x-2"
            >
              <button class="btn btn-active btn-primary ">
                Learn more about MetaStock
              </button>
              <button class="btn btn-active btn-secondary">
                What's new in MetaStock
              </button>
            </div>
          </div>
        </div>
        <!-- <div class="divider divider-horizontal"></div> -->
        <div class="grid h-auto md:w-1/3 flex-grow card  place-items-center ">
          <div class="lg-circle w-40 h-40 bg-green-400 rounded-full">
            &nbsp;
          </div>
          <img
            width="417"
            height="348"
            class=" w-full max-w-[417px] h-auto object-cover transition-all "
            src="https://www.metastock.com/images/w/MS-Montor-417px.png"
            alt=""
          >
        </div>
      </div>
    </div>
  </section>

  <!-- ====================== hidden =================================== -->

  <div class="hidden">
    <div class="grid grid-cols-3">
      <h1 class="bg-green-200 col-span-2">
        Hey Hey, were the mongeese
      </h1>
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
