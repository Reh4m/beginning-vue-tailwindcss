<template>
  <footer class="py-10">
    <div
      class="flex flex-col md:flex-row md:justify-between max-w-6xl mx-auto md:space-y-0 items-center"
    >
      <div class="text-center text-slate-600 text-sm">
        &copy; {{ currentYear }} All rights reserved.
      </div>
      <div class="flex space-x-4">
        <Icons
          v-for="logo in logos"
          :key="logo.id"
          :id="logo.id"
          :name="logo.name"
          :color="getColorClass(logo.id)"
          :path="logo.path"
        />
      </div>
    </div>
  </footer>
</template>

<script>
import Icons from "@/components/Icons.vue";
import logos from "@/data/logos.json";

const colorMap = {
  1: "hover:text-[#1877f2]", // Facebook
  2: "hover:text-[#1da1f2]", // Twitter
  3: "hover:text-[#c13584]", // Instagram
  4: "hover:text-[#333]", // GitHub
  5: "hover:text-[#25d366]", // WhatsApp
};

export default {
  name: "Footer",
  components: {
    Icons,
  },
  data: () => ({
    logos: logos.social,
    currentYear: new Date().getFullYear(),
  }),
  methods: {
    getColorClass(id) {
      return colorMap[id];
    },
  },
};
</script>
