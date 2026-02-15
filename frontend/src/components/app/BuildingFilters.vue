<script setup lang="ts">
import { ref } from "vue";
import { Button } from "@/components/ui/button";
import { Label } from "@/components/ui/label";
import { Popover, PopoverContent, PopoverTrigger } from "@/components/ui/popover";
import {
  Accordion,
  AccordionContent,
  AccordionItem,
  AccordionTrigger,
} from "@/components/ui/accordion";
import { RadioGroup, RadioGroupItem } from "@/components/ui/radio-group";
import { Funnel } from "lucide-vue-next";

const roomType = ref("");
const roomCapacity = ref("");
const durationFree = ref("");
const location = ref("");
const idRequired = ref("");

function reset() {
  roomType.value = "";
  roomCapacity.value = "";
  durationFree.value = "";
  location.value = "";
  idRequired.value = "";
}
</script>

<template>
  <Popover>
    <PopoverTrigger as-child>
      <Button variant="outline"> <Funnel /> Filters </Button>
    </PopoverTrigger>
    <PopoverContent class="p-0" align="start">
      <div class="flex items-center justify-between p-4 border-b">
        <h4 class="text-lg font-bold">Filter</h4>
        <Button
          @click="reset"
          class="px-0 py-0 h-fit hover:bg-transparent hover:underline dark:hover:bg-transparent bg-transparent text-destructive"
        >
          Reset
        </Button>
      </div>
      <Accordion type="multiple" class="w-full max-h-70 overflow-y-scroll p-0.5">
        <AccordionItem value="roomType">
          <AccordionTrigger class="p-4">Room Type</AccordionTrigger>
          <AccordionContent class="p-4">
            <RadioGroup v-model="roomType">
              <div
                class="flex items-center gap-2"
                v-for="option in [
                  'Auditorium',
                  'Computer Lab',
                  'Lab',
                  'Lecture Hall',
                  'Meeting Room',
                  'Studio',
                  'Tutorial Room',
                  'Library Study Room',
                ]"
                :key="option"
              >
                <RadioGroupItem :value="option" :id="`roomType-${option}`" />
                <Label :for="`roomType-${option}`">{{ option }}</Label>
              </div>
            </RadioGroup>
          </AccordionContent>
        </AccordionItem>

        <AccordionItem value="roomCapacity">
          <AccordionTrigger class="p-4">Room Capacity</AccordionTrigger>
          <AccordionContent class="p-4">
            <RadioGroup v-model="roomCapacity">
              <div
                class="flex items-center gap-2"
                v-for="option in ['25+', '50+', '100+', '200+']"
                :key="option"
              >
                <RadioGroupItem :value="option" :id="`capacity-${option}`" />
                <Label :for="`capacity-${option}`">{{ option }}</Label>
              </div>
            </RadioGroup>
          </AccordionContent>
        </AccordionItem>

        <AccordionItem value="durationFree">
          <AccordionTrigger class="p-4">Duration Free</AccordionTrigger>
          <AccordionContent class="p-4">
            <RadioGroup v-model="durationFree">
              <div
                class="flex items-center gap-2"
                v-for="option in ['30+ minutes', '1+ hours', '2+ hours', '3+ hours']"
                :key="option"
              >
                <RadioGroupItem :value="option" :id="`duration-${option}`" />
                <Label :for="`duration-${option}`">{{ option }}</Label>
              </div>
            </RadioGroup>
          </AccordionContent>
        </AccordionItem>

        <AccordionItem value="location">
          <AccordionTrigger class="p-4">Location</AccordionTrigger>
          <AccordionContent class="p-4">
            <RadioGroup v-model="location">
              <div
                class="flex items-center gap-2"
                v-for="option in ['Upper Campus', 'Lower Campus']"
                :key="option"
              >
                <RadioGroupItem :value="option" :id="`location-${option}`" />
                <Label :for="`location-${option}`">{{ option }}</Label>
              </div>
            </RadioGroup>
          </AccordionContent>
        </AccordionItem>

        <AccordionItem value="idRequired">
          <AccordionTrigger class="p-4">ID Required</AccordionTrigger>
          <AccordionContent class="p-4">
            <RadioGroup v-model="idRequired">
              <div
                class="flex items-center gap-2"
                v-for="option in ['Not Required', 'Required']"
                :key="option"
              >
                <RadioGroupItem :value="option" :id="`id-${option}`" />
                <Label :for="`id-${option}`">{{ option }}</Label>
              </div>
            </RadioGroup>
          </AccordionContent>
        </AccordionItem>
      </Accordion>
    </PopoverContent>
  </Popover>
</template>
