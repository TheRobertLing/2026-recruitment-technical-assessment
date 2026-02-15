<script setup lang="ts">
import { Search } from "lucide-vue-next";

import { InputGroup, InputGroupAddon, InputGroupInput } from "@/components/ui/input-group";
</script>

<template>
  <InputGroup>
    <InputGroupInput placeholder="Search for a building..." />
    <InputGroupAddon>
      <Search />
    </InputGroupAddon>
  </InputGroup>
</template>
