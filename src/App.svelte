<script>
  const bullets = [...Array(30).keys()];
</script>

<style type="text/scss">
/*
$_precision: 10;
@function sin($angle){
  $a: _to_unitless_rad($angle);
  $sin: $a;
  @for $n from 1 through $_precision {
    $sin: $sin + (pow(-1, $n) / fact(2 * $n + 1) ) * pow($a, (2 * $n + 1));
  }
  @return $sin;
}

@function cos($angle){
  $a: _to_unitless_rad($angle);
  $cos: 1;
  @for $n from 1 through $_precision {
    $cos: $cos + ( pow(-1,$n) / fact(2*$n) ) * pow($a,2*$n);
  }
  @return $cos;
}
*/
  .bora {
    width:300px;
    animation: anime 0.1s linear infinite;
  }
  .bullet-base {
    
  }

  $startDeg:15;
  $rotateRange:45;
  @keyframes anime {
    0% {
      transform: rotate(random($rotateRange)+$startDeg+deg);
    }
    10% {
      transform: rotate(random($rotateRange)+$startDeg+deg);
    }
    20% {
      transform: rotate(random($rotateRange)+$startDeg+deg);
    }
    30% {
      transform: rotate(random($rotateRange)+$startDeg+deg);
    }
    40% {
      transform: rotate(random($rotateRange)+$startDeg+deg);
    }
    50% {
      transform: rotate(random($rotateRange)+$startDeg+deg);
    }
    60% {
      transform: rotate(random($rotateRange)+$startDeg+deg);
    }
    70% {
      transform: rotate(random($rotateRange)+$startDeg+deg);
    }
    80% {
      transform: rotate(random($rotateRange)+$startDeg+deg);
    }
    90% {
      transform: rotate(random($rotateRange)+$startDeg+deg);
    }
    100% {
      transform: rotate(random($rotateRange)+$startDeg+deg);
    }
  }

  $bulletSpeed:10;
  @for $i from 0 through 30-1 {
    $deg:random($rotateRange)+$startDeg;
    #bullet-#{$i} {
      @keyframes bullet-anime-#{$i} {
        0%{
          transform:translate(0,0);
        }
        100%{
          $x:calc(#{$bulletSpeed}px + #{cos($deg)}px);
          /* $y:($bulletSpeed*sin($deg))+px; */
          transform:translate($x,0);
        }
      }
      animation: bullet-anime-#{$i} 0.1s linear infinite;
    }
  }


</style>

<main>
  <img class="bora" src="fish_bora.png" alt="bora" />
  {#each bullets as bullet}
    <img class="bullet-base" id="bullet-{bullet}" src="gin_dangan_silver_bullet.png" alt="bullet">
  {/each}
</main>
