<template>
  <div>
    <b-pagination
      v-model="currentPage"
      :total-rows="rows"
      :per-page="perPage"
      aria-controls="itemList"
      align="center"
    ></b-pagination>
    <ul id="itemList">
      <li v-for="item in itemsForList" :key="item.id">
        <h1>{{item.header}}</h1>
        <span>{{item.text}}</span>
      </li>
    </ul>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component
export default class HelloWorld extends Vue {
  currentPage = 1;

  perPage = 3;

  data = [
    {
      header: 'item 1',
      text: '❤️',
      id: 1,
    },
    {
      header: 'item 2',
      text: '🗿',
      id: 2,
    },
    {
      header: 'item 3',
      text: '⛺️',
      id: 3,
    },
    {
      header: 'item 4',
      text: '🌄',
      id: 4,
    },
    {
      header: 'item 5',
      text: '💎',
      id: 5,
    },
    {
      header: 'item 6',
      text: '⏳',
      id: 6,
    },
    {
      header: 'item 7',
      text: '🧱',
      id: 7,
    },
  ];

  rows = this.data.length;

  get itemsForList() {
    return this.data.slice(
      (this.currentPage - 1) * this.perPage,
      this.currentPage * this.perPage,
    );
  }
}
</script>
