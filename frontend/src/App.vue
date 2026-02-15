<script setup lang="ts">
import HeaderLogo from "./components/app/HeaderLogo.vue";
import HeaderSearch from "./components/app/HeaderSearch.vue";
import HeaderViewToggle from "./components/app/HeaderViewToggle.vue";
import HeaderMap from "./components/app/HeaderMap.vue";
import HeaderThemeToggle from "./components/app/HeaderThemeToggle.vue";

import BuildingSearchBar from "./components/app/BuildingSearchBar.vue";
import BuildingFilters from "./components/app/BuildingFilters.vue";
import BuildingSort from "./components/app/BuildingSort.vue";
import BuildingCard from "./components/app/BuildingCard.vue";

import agsm from "@/assets/agsm.webp";
import ainsworth from "@/assets/ainsworth.webp";
import anitab from "@/assets/anitab.webp";
import biologicalScience from "@/assets/biologicalScience.webp";
import biologicalScienceWest from "@/assets/biologicalScienceWest.webp";
import blockhouse from "@/assets/blockhouse.webp";
import businessSchool from "@/assets/businessSchool.webp";
import civilBuilding from "@/assets/civilBuilding.webp";
import colombo from "@/assets/colombo.webp";
import cseBuilding from "@/assets/cseBuilding.webp";

const buildings = [
  { name: "AGSM", roomsAvailable: 9, image: agsm },
  { name: "Ainsworth Building", roomsAvailable: 16, image: ainsworth },
  { name: "Anita B Lawrence Centre", roomsAvailable: 44, image: anitab },
  { name: "Biological Sciences", roomsAvailable: 6, image: biologicalScience },
  { name: "Biological Sciences (West)", roomsAvailable: 8, image: biologicalScienceWest },
  { name: "Blockhouse", roomsAvailable: 42, image: blockhouse },
  { name: "Business School", roomsAvailable: 18, image: businessSchool },
  { name: "Civil Engineering Building", roomsAvailable: 8, image: civilBuilding },
  { name: "Colombo Building", roomsAvailable: 5, image: colombo },
  { name: "Computer Science & Eng (K17)", roomsAvailable: 7, image: cseBuilding },
];
</script>

<template>
  <header class="border-b sticky top-0 bg-background z-10">
    <div class="max-w-7xl w-full flex items-center justify-between mx-auto p-2">
      <div class="flex items-center gap-0">
        <HeaderLogo />
      </div>

      <div class="flex items-center gap-2">
        <HeaderSearch />
        <HeaderViewToggle />
        <HeaderMap />
        <HeaderThemeToggle />
      </div>
    </div>
  </header>
  <main>
    <div class="max-w-7xl w-full mx-auto p-2 space-y-4 mt-2">
      <div class="hidden sm:flex items-center justify-between gap-2">
        <BuildingFilters />
        <BuildingSearchBar class="flex-1 max-w-2xl mx-auto" />
        <BuildingSort />
      </div>

      <div class="flex flex-col gap-2 sm:hidden">
        <BuildingSearchBar />
        <div class="flex items-center justify-between">
          <BuildingFilters />
          <BuildingSort />
        </div>
      </div>

      <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4">
        <BuildingCard
          v-for="building in buildings"
          :key="building.name"
          :name="building.name"
          :rooms-available="building.roomsAvailable"
          :image="building.image"
        />
      </div>
    </div>
  </main>
</template>
