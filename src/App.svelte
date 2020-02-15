<script>
  const bullets = [...Array(30).keys()];
</script>

<style type="text/scss">
  main {
    width:100%;
    height:100%;
  }
  .container {
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: flex-start;
    align-items: flex-start;
  }
  .bora {
    width: 300px;
    animation: anime 0.15s linear infinite;
    z-index: 1;
  }
  .bullet-base {
    position: absolute;
    top:120px;
    left:150px;
    z-index: 0;
  }

  $startDeg: 15;
  $rotateRange: 45;
  @keyframes anime {
    0% {
      transform: rotate(random($rotateRange) + $startDeg + deg);
    }
    10% {
      transform: rotate(random($rotateRange) + $startDeg + deg);
    }
    20% {
      transform: rotate(random($rotateRange) + $startDeg + deg);
    }
    30% {
      transform: rotate(random($rotateRange) + $startDeg + deg);
    }
    40% {
      transform: rotate(random($rotateRange) + $startDeg + deg);
    }
    50% {
      transform: rotate(random($rotateRange) + $startDeg + deg);
    }
    60% {
      transform: rotate(random($rotateRange) + $startDeg + deg);
    }
    70% {
      transform: rotate(random($rotateRange) + $startDeg + deg);
    }
    80% {
      transform: rotate(random($rotateRange) + $startDeg + deg);
    }
    90% {
      transform: rotate(random($rotateRange) + $startDeg + deg);
    }
    100% {
      transform: rotate(random($rotateRange) + $startDeg + deg);
    }
  }

  $bulletSpeed: 100vw;
  @for $i from 0 through 30-1 {
    $deg: random($rotateRange) + $startDeg;
    #bullet-#{$i} {
      @keyframes bullet-anime-#{$i} {
        0% {
          transform: rotate($deg + deg) translate(0, 0);
        }
        100% {
          transform: rotate($deg + deg) translate($bulletSpeed, 0);
        }
      }
      animation: bullet-anime-#{$i} 0.3s linear random(10)*0.1+s infinite;
    }
  }
</style>

<main>
  <div class="container">
    <img class="bora" src="fish_bora.png" alt="bora" />
    {#each bullets as bullet}
      <img
        class="bullet-base"
        id="bullet-{bullet}"
        src="gin_dangan_silver_bullet.png"
        alt="bullet" />
    {/each}
  </div>
</main>
