<script setup lang="ts">
import { Button } from "@/components/ui/button";
import { Search } from "lucide-vue-next";
import PlaceHolderDialog from "./PlaceHolderDialog.vue";
</script>

<template>
  <PlaceHolderDialog>
    <Button variant="outline" size="icon" title="Search">
      <Search />
    </Button>
  </PlaceHolderDialog>
</template>
