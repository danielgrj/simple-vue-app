<template>
  <div class="row">
    <transition-group name="quote">
      <quote
        v-for="(quote, index) in quotes"
        :key="quote"
        @click.native="deleteQuote(index)"
      >{{quote}}</quote>
    </transition-group>
  </div>
</template>

<script>
import Quote from './Quote';

export default {
  props: ['quotes'],
  components: {
    quote: Quote
  },
  methods: {
    deleteQuote(index) {
      this.$emit('deleteQuote', index);
    }
  }
};
</script>

<style scoped>
.quote-enter-active,
.quote-leave {
  opacity: 1;
  transition: all 1s;
}

.quote-enter {
  opacity: 0;
}

.quote-leave-active {
  opacity: 0;
  transition: all 1s;
  position: absolute;
}

.quote-move {
  transition: all 1s;
}
</style>