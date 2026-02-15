<script setup lang="ts">
import {
  Dialog,
  DialogContent,
  DialogDescription,
  DialogHeader,
  DialogTitle,
  DialogTrigger,
} from "@/components/ui/dialog";
</script>

<template>
  <Dialog>
    <DialogTrigger as-child>
      <slot />
    </DialogTrigger>
    <DialogContent>
      <DialogHeader>
        <DialogTitle>Placeholder Dialog</DialogTitle>
        <DialogDescription> Placeholder dialog for unspecified/unclear requirements </DialogDescription>
      </DialogHeader>
    </DialogContent>
  </Dialog>
</template>
