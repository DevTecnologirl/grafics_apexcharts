<template>
  <div>
   <NuxtPage />
  </div>
  <!-- Wrap with ClientOnly -->
  <ClientOnly>
    <BarChart />
  </ClientOnly>
  <!-- or use the `.client.vue` extension -->
  <!-- <LineChart /> -->
</template>
