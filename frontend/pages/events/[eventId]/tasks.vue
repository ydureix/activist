<!-- SPDX-License-Identifier: AGPL-3.0-or-later -->
<template>
  <div class="flex flex-col bg-layer-0 px-4 xl:px-8">
    <Head>
      <Title>
        {{ event.name }}&nbsp;{{ $t("i18n.pages._global.tasks.tasks_lower") }}
      </Title>
    </Head>
    <HeaderAppPageEvent
      :header="event.name + ' ' + $t('i18n.pages._global.tasks.tasks_lower')"
      :tagline="$t('i18n.pages._global.tasks.tasks_page_tagline')"
      :underDevelopment="true"
    >
      <div class="flex space-x-2 lg:space-x-3">
        <BtnAction
          class="w-max"
          :cta="true"
          label="i18n.pages._global.tasks.new_task"
          fontSize="sm"
          :leftIcon="IconMap.PLUS"
          iconSize="1.35em"
          ariaLabel="i18n.pages._global.tasks.new_task_aria_label"
        />
      </div>
    </HeaderAppPageEvent>
    <!-- <div v-if="event.tasks" class="space-y-3 py-4"></div>
    <EmptyState v-else pageType="tasks" :permission="false" /> -->
  </div>
</template>

<script setup lang="ts">
import type { Event } from "~/types/events/event";

import { IconMap } from "~/types/icon-map";

defineProps<{
  event: Event;
}>();
</script>
