<template>
  <article class="bg-white shadow rounded overflow-hidden flex flex-col">
    <div class="h-52">
      <img class="h-full w-full object-contain" :src="getImageURL(id)" />
    </div>
    <div class="p-5 space-y-3 flex-1">
      <h3 class="text-sm font-semibold text-sky-500">
        {{ topic }}
      </h3>
      <h2 class="text-xl font-semibold text-slate-800 leading-tight">
        {{ title }}
      </h2>
      <p class="text-slate-500 hidden md:block">
        {{ description }}
      </p>
    </div>
    <div class="flex p-5 space-x-2">
      <img
        class="h-10 w-10 rounded-full"
        :src="getAuthorImageURL(author.firstName, author.lastName)"
        :alt="getAuthorFullName(author.firstName, author.lastName)"
      />
      <div class="flex flex-col justify-center">
        <span class="text-sm font-semibold text-slate-600 leading-4">
          {{ getAuthorFullName(author.firstName, author.lastName) }}
        </span>
        <span class="text-sm text-slate-500">
          {{ date }}
        </span>
      </div>
    </div>
  </article>
</template>

<script>
export default {
  name: "Card",
  props: {
    id: {
      type: Number,
      required: true,
    },
    topic: {
      type: String,
      required: true,
    },
    title: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      required: true,
    },
    author: {
      type: Object,
      required: true,
    },
    date: {
      type: String,
      required: true,
    },
  },
  methods: {
    getImageURL(id) {
      return `https://picsum.photos/id/${id}/600/300`;
    },
    getAuthorImageURL(firstName, lastName) {
      return `https://ui-avatars.com/api?name=${encodeURIComponent(
        `${firstName} ${lastName}`
      )}`;
    },
    getAuthorFullName(firstName, lastName) {
      return `${firstName} ${lastName}`;
    },
  },
};
</script>
