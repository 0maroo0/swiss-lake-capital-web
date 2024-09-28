<!-- eslint-disable vue/multi-word-component-names -->
<!-- eslint-disable no-unused-vars -->
<template>
  <div class="container">
    <div v-for="i in 3" :key="i" class="hs__wrapper">
      <div class="hs__header">
        <h2 class="hs__headline">Headline {{ i }}</h2>
        <div class="hs__arrows">
          <a
            :class="['arrow', 'arrow-prev', { disabled: !canScrollPrev[i] }]"
            @click="scroll(i, 'prev')"
          ></a>
          <a
            :class="['arrow', 'arrow-next', { disabled: !canScrollNext[i] }]"
            @click="scroll(i, 'next')"
          ></a>
        </div>
      </div>
      <ul
        ref="scrollContainers"
        :key="`scroll-${i}`"
        class="hs"
        @scroll="handleScroll(i)"
      >
        <li v-for="n in 20" :key="`${i}-${n}`" class="hs__item">
          <div class="hs__item__image__wrapper">
            <img
              :src="`https://picsum.photos/id/${10 + n + i}/300/300`"
              alt=""
              class="hs__item__image"
            />
          </div>
          <div class="hs__item__description">
            <span class="hs__item__title">Amazing title {{ n }}</span>
            <span class="hs__item__subtitle">some subtitle</span>
          </div>
        </li>
      </ul>
    </div>

    <div class="description">
      <h3>Description</h3>
      <p>
        <strong>Work in progress</strong> – Horizontal scroll containers are
        hyped right now...
      </p>
    </div>
  </div>
</template>
<!-- ?   -->
<script>
import { ref, nextTick } from "vue";

export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Slider",
  setup() {
    const canScrollPrev = ref({});
    const canScrollNext = ref({});

    const updateArrowStates = () => {
      const containers = Array.isArray(this.$refs.scrollContainers)
        ? this.$refs.scrollContainers
        : [this.$refs.scrollContainers];

      containers.forEach((container, i) => {
        const scrollLeft = container.scrollLeft;
        const maxScrollLeft = container.scrollWidth - container.clientWidth;

        // Directly assign values to the reactive refs
        canScrollPrev.value[i + 1] = scrollLeft > 0;
        canScrollNext.value[i + 1] = scrollLeft < maxScrollLeft;
      });
    };

    const scroll = (index, direction) => {
      const container = this.$refs.scrollContainers[index - 1];
      if (!container) return;

      const scrollAmount = container.clientWidth / 2;
      container.scrollBy({
        left: direction === "next" ? scrollAmount : -scrollAmount,
        behavior: "smooth",
      });
    };

    const handleScroll = (index) => {
      updateArrowStates(index);
    };

    return {
      canScrollPrev,
      canScrollNext,
      scroll,
      handleScroll,
      updateArrowStates,
    };
  },
  mounted() {
    nextTick(() => {
      this.updateArrowStates();
    });
  },
};
</script>

<style scoped>
.container {
  max-width: 990px;
  margin: 0 auto;
  background: #121212;
  position: relative;
  padding: 20px;
}

.hs {
  display: flex;
  overflow-x: scroll;
  scrollbar-width: none; /* Firefox */
  -ms-overflow-style: none; /* IE 10+ */
  -webkit-overflow-scrolling: touch;
  margin: 0 -20px;
}

.hs__header {
  display: flex;
  align-items: center;
  width: 100%;
}

.hs__headline {
  flex: 1;
}

.hs__arrows {
  align-self: center;
}

.arrow {
  display: inline-block;
  width: 18px;
  height: 12px;
  cursor: pointer;
}

.arrow-prev::before,
.arrow-next::before {
  content: "";
  display: block;
  width: 18px;
  height: 12px;
  background: url("data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIxNSIgaGVpZ2h0PSI5IiB2aWV3Qm94PSIwIDAgMTUgOSI+Cgk8cGF0aCBmaWxsPSIjMzMzMzMzIiBkPSJNNy44NjcgOC41NzRsLTcuMjItNy4yMi43MDctLjcwOEw3Ljg2NyA3LjE2IDE0LjA1Ljk4bC43MDYuNzA3Ii8+Cjwvc3ZnPgo=")
    no-repeat center center;
  filter: brightness(5);
  background-size: contain;
}

.arrow-prev.disabled::before,
.arrow-next.disabled::before {
  filter: brightness(2);
}

.arrow-prev::before {
  transform: rotate(90deg);
}

.arrow-next::before {
  transform: rotate(-90deg);
}

.hs__item {
  flex-shrink: 0;
  width: calc(25% - 20px);
  margin: 10px;
}

.hs__item__image__wrapper {
  position: relative;
  width: 100%;
  height: 0;
  padding-bottom: 100%;
}

.hs__item__image {
  position: absolute;
  width: 100%;
  height: 100%;
  object-fit: cover;
}
</style>
