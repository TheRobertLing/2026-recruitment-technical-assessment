<script setup lang="ts">
import openDoor from "@/assets/freeRoomsLogo.png";
import closedDoor from "@/assets/freeroomsDoorClosed.png";
import { Button } from "@/components/ui/button";
import { useToggle } from "@vueuse/shared";

const [isDoorOpen, toggleDoor] = useToggle(false);
</script>

<template>
  <Button
    variant="ghost"
    class="hover:bg-transparent dark:hover:bg-transparent px-1 py-1 h-fit gap-0"
    title="Freerooms"
    @click="toggleDoor()"
  >
    <img :src="isDoorOpen ? openDoor : closedDoor" class="size-9" />
    <h1
      class="sr-only sm:not-sr-only text-2xl font-semibold tracking-tight select-none text-primary"
    >
      Freerooms
    </h1>
  </Button>
</template>
