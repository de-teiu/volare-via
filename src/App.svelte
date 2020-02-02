<script>

</script>

<style type="text/scss">
  .bora {
    @for $i from 1 through 10 {
      animation: "anime" + $i 1s ease ($i - 1) s alternate forwards;
    }
  }
</style>

<main>
  <img class="bora" src="fish_bora.png" alt="bora" />
</main>
