<template>
  <a href="#">
    <svg
      class="w-6 duration-300 text-slate-500 fill-current"
      :class="color"
      role="img"
      viewBox="0 0 24 24"
      xmlns="http://www.w3.org/2000/svg"
    >
      <title>{{ name }}</title>
      <path :d="path" />
    </svg>
  </a>
</template>

<script>
export default {
  name: "Icons",
  props: {
    id: {
      type: Number,
      required: true,
    },
    name: {
      type: String,
      required: true,
    },
    color: {
      type: String,
      required: true,
    },
    path: {
      type: String,
      required: true,
    },
  },
};
</script>
