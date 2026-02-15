<script setup lang="ts">
import { Button } from "@/components/ui/button";
import { Map } from "lucide-vue-next";
import PlaceHolderDialog from "./PlaceHolderDialog.vue";
</script>

<template>
  <PlaceHolderDialog>
    <Button variant="outline" size="icon" title="Map View">
      <Map />
    </Button>
  </PlaceHolderDialog>
</template>
