<template>
  <q-page>
    <div class="row justify-center q-mt-sm">
      <div class="q-pa-xs col-8">
        <q-card @click="launch()">
          <q-card-section>
            <q-img alt="Begeleider" src="~assets/begeleider.png" />
          </q-card-section>
        </q-card>
      </div>
    </div>
  </q-page>
</template>

<script setup>
import { useQuasar } from "quasar";

const { dialog } = useQuasar();
const launch = () => {
  dialog({
    title: "Enter the space",
    position: "top",
    cancel: true,
    prompt: {
      model: "",
      isValid: (val) => val != "",
    },
  }).onOk((value) => {
    window.open(
      `https://begeleider.book-mm.com/login?tenant=${value}`,
      "_blank"
    );
  });
};
</script>
