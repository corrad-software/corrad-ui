<script setup>
definePageMeta({
  title: "Card",
});

const showCode = ref(false);
const showCode2 = ref(false);
</script>

<template>
  <div>
    <LayoutsBreadcrumb />
    <rs-card>
      <template #header>
        <h5>Default Card</h5>
      </template>
      <template #body>
        <p class="mb-2">
          Use the <code>rs-card</code> component to create a card layout.
        </p>
        <rs-card class="mb-4">
          <template #header>
            <h6>Card Header</h6>
          </template>
          <template #body>
            <p>This is the main content of the card.</p>
          </template>
          <template #footer>
            <p>Card Footer</p>
          </template>
        </rs-card>
        <div class="flex justify-end">
          <button
            class="text-sm border border-slate-200 py-1 px-3 rounded-lg"
            @click="showCode = !showCode"
          >
            Show Code
          </button>
        </div>
        <ClientOnly>
          <transition name="fade">
            <div v-show="showCode" v-highlight>
              <NuxtScrollbar style="height: 400px">
                <pre class="language-html shadow-none">
                  <code>
                    &lt;template&gt;
                      &lt;rs-card&gt;
                        &lt;template #header&gt;
                          &lt;h6&gt;Card Header&lt;/h6&gt;
                        &lt;/template&gt;
                        &lt;template #body&gt;
                          &lt;p&gt;This is the main content of the card.&lt;/p&gt;
                        &lt;/template&gt;
                        &lt;template #footer&gt;
                          &lt;p&gt;Card Footer&lt;/p&gt;
                        &lt;/template&gt;
                      &lt;/rs-card&gt;
                    &lt;/template&gt;

                    &lt;script setup&gt;&lt;/script&gt;
                  </code>
                </pre>
              </NuxtScrollbar>
            </div>
          </transition>
        </ClientOnly>
      </template>
    </rs-card>

    <rs-card>
      <template #header>
        <h5>Card with Main Slot</h5>
      </template>
      <template #body>
        <p class="mb-2">
          You can use the default slot to add content directly to the card
          without using the body slot.
        </p>
        <rs-card class="mb-4">
          <p>This content is added using the default slot.</p>
        </rs-card>
        <div class="flex justify-end">
          <button
            class="text-sm border border-slate-200 py-1 px-3 rounded-lg"
            @click="showCode2 = !showCode2"
          >
            Show Code
          </button>
        </div>
        <ClientOnly>
          <transition name="fade">
            <div v-show="showCode2" v-highlight>
              <NuxtScrollbar style="height: 400px">
                <pre class="language-html shadow-none">
                  <code>
                    &lt;template&gt;
                      &lt;rs-card&gt;
                        &lt;p&gt;This content is added using the default slot.&lt;/p&gt;
                      &lt;/rs-card&gt;
                    &lt;/template&gt;

                    &lt;script setup&gt;&lt;/script&gt;
                  </code>
                </pre>
              </NuxtScrollbar>
            </div>
          </transition>
        </ClientOnly>
      </template>
    </rs-card>
  </div>
</template>

<style scoped lang="scss">
// Add any specific styles here
</style>
