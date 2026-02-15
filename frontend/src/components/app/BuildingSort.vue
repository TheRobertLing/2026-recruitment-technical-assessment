<script setup lang="ts">
import { ref } from "vue";
import { Button } from "@/components/ui/button";
import { Label } from "@/components/ui/label";
import { Popover, PopoverContent, PopoverTrigger } from "@/components/ui/popover";
import { RadioGroup, RadioGroupItem } from "@/components/ui/radio-group";
import { ArrowUpDown } from "lucide-vue-next";

const sortBy = ref("");

const options = [
  "Most Available Rooms",
  "Nearest",
  "Alphabetical",
  "Reverse Alphabetical",
  "Lower Campus",
  "Upper Campus",
];

function reset() {
  sortBy.value = "";
}
</script>

<template>
  <Popover>
    <PopoverTrigger as-child>
      <Button variant="outline"> <ArrowUpDown /> Sort </Button>
    </PopoverTrigger>
    <PopoverContent class="p-0" align="end">
      <div class="flex items-center justify-between px-4 py-3 border-b">
        <h4 class="text-lg font-bold">Sort</h4>
        <Button
          @click="reset"
          class="px-0 py-0 h-fit hover:bg-transparent hover:underline dark:hover:bg-transparent bg-transparent text-destructive"
        >
          Reset
        </Button>
      </div>

      <RadioGroup
        :model-value="sortBy"
        @update:model-value="
          (e) => {
            sortBy = e === sortBy ? '' : e;
          }
        "
        class="p-4"
      >
        <div class="flex items-center gap-2" v-for="option in options" :key="option">
          <RadioGroupItem :value="option" :id="`sort-${option}`" />
          <Label :for="`sort-${option}`">{{ option }}</Label>
        </div>
      </RadioGroup>
    </PopoverContent>
  </Popover>
</template>
