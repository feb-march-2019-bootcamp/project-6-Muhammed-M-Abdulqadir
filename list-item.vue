 <template>
  <li @click="toggleClass" :class="{'active': isActive}">
    <slot></slot>
  </li>
</template>
 <script>
export default {
  data() {
    return {
      items: [
        { description: "Web Development", price: 300 },
        { description: "Design", price: 400 },
        { description: "Integration", price: 500 },
        { description: "Training", price: 200 }
      ],
      total: 0,
      isActive: false
    };
  },

  methods: {
    toggleClass() {
      this.isActive = !this.isActive;

      this.items.forEach(element => {
        if (this.isActive) {
          this.total = this.total + element.price;
        } else {
          this.total = this.total - element.price;
        }
      });
    }
  }
};
</script>
