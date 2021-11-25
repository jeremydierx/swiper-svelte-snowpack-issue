<script>
  /* component logic will go here */
  // Import Swiper Svelte components
  import { Swiper, SwiperSlide } from 'swiper/svelte';

  // Import Swiper styles
  import 'swiper/css';
</script>
<style>
  /* css will go here */
</style>
<div class="App">
  <header class="App-header">
    <a class="App-link" href="https://svelte.dev" target="_blank" rel="noopener noreferrer">
      Learn Svelte
    </a>
  </header>

  <Swiper
    spaceBetween={50}
    slidesPerView={3}
    on:slideChange={() => console.log('slide change')}
    on:swiper={(e) => console.log(e.detail[0])}
  >
    <SwiperSlide>Slide 1</SwiperSlide>
    <SwiperSlide>Slide 2</SwiperSlide>
    <SwiperSlide>Slide 3</SwiperSlide>
    <SwiperSlide>Slide 4</SwiperSlide>
    ...
  </Swiper>

</div>