<!-- SPDX-License-Identifier: AGPL-3.0-or-later -->
<template>
  <button
    :id="id"
    class="btn-base-class rounded-md xl:rounded-lg"
    :class="btnDynamicClass"
    :aria-label="$t(ariaLabel)"
  >
    <BtnIconsLabel
      :label="label"
      :hideLabelOnMobile="hideLabelOnMobile"
      :leftIcon="leftIcon"
      :rightIcon="rightIcon"
      :iconSize="iconSize"
      :counter="counter"
    />
  </button>
</template>

<script setup lang="ts">
import type { BtnAction } from "~/types/btn-props";

import { getBtnDynamicClass } from "~/utils/btnUtils";

const props = defineProps<BtnAction>();

function loadBtnDynamicClass() {
  return getBtnDynamicClass(props.cta, props.fontSize);
}

let btnDynamicClass = loadBtnDynamicClass();

watchEffect(() => {
  btnDynamicClass = loadBtnDynamicClass();
});
</script>
