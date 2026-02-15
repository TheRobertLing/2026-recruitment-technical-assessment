<script setup lang="ts">
import { Button } from "@/components/ui/button";
import { LayoutGrid } from "lucide-vue-next";
import PlaceHolderDialog from "./PlaceHolderDialog.vue";
</script>

<template>
  <PlaceHolderDialog>
    <Button variant="default" size="icon" title="Toggle View">
      <LayoutGrid />
    </Button>
  </PlaceHolderDialog>
</template>
