<script setup lang="ts">
import { Badge } from "@/components/ui/badge";
import { Button } from "@/components/ui/button";
import {
  Sheet,
  SheetContent,
  SheetDescription,
  SheetHeader,
  SheetTitle,
  SheetTrigger,
} from "@/components/ui/sheet";
import { Item, ItemContent, ItemTitle } from "@/components/ui/item";

defineProps<{
  name: string;
  roomsAvailable: number;
  image: string;
}>();
</script>

<template>
  <Sheet>
    <SheetTrigger as-child>
      <Button class="group hidden sm:block relative h-100 w-full px-0 py-0 rounded-xl">
        <img
          :src="image"
          :alt="name"
          class="size-full object-cover rounded-xl group-hover:opacity-70 transition-opacity"
        />

        <Badge
          class="absolute top-2 right-2 bg-background/70 backdrop-blur-md text-foreground px-3 py-2 gap-2"
        >
          <span class="size-2 rounded-full bg-green-500" />
          {{ roomsAvailable }} rooms available
        </Badge>

        <div
          class="absolute inset-x-0 bottom-0 h-1/2 bg-linear-to-t from-black/80 via-black/40 to-transparent rounded-xl"
        />

        <div class="absolute bottom-3 left-3 right-3">
          <span class="font-bold text-base text-white drop-shadow-md">{{ name }}</span>
        </div>
      </Button>
    </SheetTrigger>

    <SheetTrigger as-child>
      <Button class="sm:hidden relative w-full h-fit px-0 py-0 rounded-xl bg-black">
        <Item class="relative w-full inset-0">
          <img
            :src="image"
            :alt="name"
            class="absolute inset-0 size-full object-cover opacity-70 rounded-xl"
          />
          <ItemContent class="relative">
            <ItemTitle class="font-bold text-white line-clamp-1">{{ name }}</ItemTitle>
          </ItemContent>
          <ItemContent class="relative flex-col items-center gap-1.5">
            <Badge class="bg-background/70 backdrop-blur-md text-foreground px-3 py-2 gap-2">
              <span class="size-2 rounded-full bg-green-500" />
              {{ roomsAvailable }} / {{ roomsAvailable }}
            </Badge>
          </ItemContent>
        </Item>
      </Button>
    </SheetTrigger>

    <SheetContent>
      <SheetHeader>
        <SheetTitle>{{ name }}</SheetTitle>
        <SheetDescription
          >Not enough stub data to build this part out really but you get the idea, show all the
          available rooms in a list and stuff</SheetDescription
        >
      </SheetHeader>
    </SheetContent>
  </Sheet>
</template>
