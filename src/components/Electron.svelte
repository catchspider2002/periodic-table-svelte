<script>
  //   import Circle from "./Circle.svelte";
  let r = 25;
  let A45 = 0.7071;
  let A90sin = 1;
  let A90cos = 0;
  let A0sin = 0;
  let A0cos = 1;
  let A10sin = 0.173648178;
  let A10cos = 0.984807753;
  let A30sin = 0.5;
  let A30cos = 0.8660254;
  let A50sin = 0.766044443;
  let A50cos = 0.6427876;
  let A70sin = 0.93969262;
  let A70cos = 0.34202;
  let A11sin = 0.19509032201612826784828486847702;
  let A11cos = 0.98078528040323044912618223613424;
  let A22sin = 0.3826834323650897717284599840304;
  let A22cos = 0.92387953251128675612818318939679;
  let A33sin = 0.55557023301960222474283081394853;
  let A33cos = 0.83146961230254523707878837761791;
  export let num = 111;
  export let sym = "H";
  export let fontcolor,
    strokecolor,
    val1 = -800,
    val2 = 1600;

  let rad1 = 230;
  let rad2 = 320;
  let rad3 = 410;
  let rad4 = 500;
  let rad5 = 590;
  let rad6 = 680;
  let rad7 = 770;
  let ringSize = 8,
    multiplier = 0;

    
  if (num > 86) multiplier = 0;
  else if (num > 54) multiplier = 1;
  else if (num > 36 && num != 46) multiplier = 2;
  else if (num > 18) multiplier = 3;
  else if (num > 10) multiplier = 4;
  else if (num > 2) multiplier = 5;
  else multiplier = 6;

  val1 = -800 + multiplier * 80
  val2 = 1600 - multiplier * 80 * 2
  
</script>

<style>
  .g {
    fill: rgb(var(--text-color));
    stroke: rgb(var(--text-color));
  }
  .nucleus {
    /* transition: all 0.5s ease-in-out; */
    fill: rgb(var(--text-color));
    stroke: rgb(var(--text-color));
  }

  .font-fam {
    font-size: 5em;
    font-weight: 500;
    fill: var(--alt-text-color);
  }
  .electron {
    transition: all 0.1s ease-in-out;
  }
  @keyframes rotate {
    0% {
      transform: rotate(0);
    }
    100% {
      transform: rotate(360deg);
    }
  }
</style>

<svg version="1.1" xmlns="http://www.w3.org/2000/svg" viewBox="-800 {val1} 1600 {val2}" class="atom">
  <g class="g">
    <circle class="nucleus" r="130" />
    <text class="font-fam" x="0" y="0" fill={fontcolor} alignment-baseline="middle" dominant-baseline="middle" text-anchor="middle">{sym}</text>

    {#if num > 0}
      <g class="one">
        <circle r={rad1} fill="none" stroke={strokecolor} stroke-width={ringSize} />
        <circle class="electron" fill={strokecolor} cx={-A0sin * rad1} cy={-A0cos * rad1} {r} />
        {#if num > 1}
          <circle class="electron" fill={strokecolor} cx={A0sin * rad1} cy={A0cos * rad1} {r} />
        {/if}
      </g>
    {/if}

    {#if num > 2}
      <g class="two">
        <circle r={rad2} fill="none" stroke={strokecolor} stroke-width={ringSize} />
        <circle class="electron" fill={strokecolor} cx={-A0sin * rad2} cy={-A0cos * rad2} {r} />
        {#if num > 3}
          <circle class="electron" fill={strokecolor} cx={A0sin * rad2} cy={A0cos * rad2} {r} />
        {/if}
        {#if num > 4}
          <circle class="electron" fill={strokecolor} cx={-A90sin * rad2} cy={A90cos * rad2} {r} />
        {/if}
        {#if num > 5}
          <circle class="electron" fill={strokecolor} cx={A90sin * rad2} cy={A90cos * rad2} {r} />
        {/if}
        {#if num > 6}
          <circle class="electron" fill={strokecolor} cx={-A45 * rad2} cy={-A45 * rad2} {r} />
        {/if}
        {#if num > 7}
          <circle class="electron" fill={strokecolor} cx={A45 * rad2} cy={-A45 * rad2} {r} />
        {/if}
        {#if num > 8}
          <circle class="electron" fill={strokecolor} cx={-A45 * rad2} cy={A45 * rad2} {r} />
        {/if}
        {#if num > 9}
          <circle class="electron" fill={strokecolor} cx={A45 * rad2} cy={A45 * rad2} {r} />
        {/if}
      </g>
    {/if}

    {#if num > 10}
      <g class="three">
        <circle r={rad3} fill="none" stroke={strokecolor} stroke-width={ringSize} />
        <circle class="electron" fill={strokecolor} cx={-A0sin * rad3} cy={-A0cos * rad3} {r} />
        {#if num > 11}
          <circle class="electron" fill={strokecolor} cx={A0sin * rad3} cy={A0cos * rad3} {r} />
        {/if}
        {#if num > 12}
          <circle class="electron" fill={strokecolor} cx={-A10cos * rad3} cy={-A10sin * rad3} {r} />
        {/if}
        {#if num > 13}
          <circle class="electron" fill={strokecolor} cx={A10cos * rad3} cy={-A10sin * rad3} {r} />
        {/if}
        {#if num > 14}
          <circle class="electron" fill={strokecolor} cx={-A30cos * rad3} cy={A30sin * rad3} {r} />
        {/if}
        {#if num > 15}
          <circle class="electron" fill={strokecolor} cx={A30cos * rad3} cy={A30sin * rad3} {r} />
        {/if}
        {#if num > 16}
          <circle class="electron" fill={strokecolor} cx={-A50cos * rad3} cy={-A50sin * rad3} {r} />
        {/if}
        {#if num > 17}
          <circle class="electron" fill={strokecolor} cx={A50cos * rad3} cy={-A50sin * rad3} {r} />
        {/if}

        {#if num > 20}
          <circle class="electron" fill={strokecolor} cx={-A50cos * rad3} cy={A50sin * rad3} {r} />
        {/if}
        {#if num > 21}
          <circle class="electron" fill={strokecolor} cx={A50cos * rad3} cy={A50sin * rad3} {r} />
        {/if}
        {#if num > 22}
          <circle class="electron" fill={strokecolor} cx={-A30cos * rad3} cy={-A30sin * rad3} {r} />
        {/if}
        {#if num > 23}
          <circle class="electron" fill={strokecolor} cx={A30cos * rad3} cy={-A30sin * rad3} {r} />
          <circle class="electron" fill={strokecolor} cx={-A10cos * rad3} cy={A10sin * rad3} {r} />
        {/if}

        {#if num > 25}
          <circle class="electron" fill={strokecolor} cx={A10cos * rad3} cy={A10sin * rad3} {r} />
        {/if}
        {#if num > 26}
          <circle class="electron" fill={strokecolor} cx={-A70cos * rad3} cy={-A70sin * rad3} {r} />
        {/if}
        {#if num > 27}
          <circle class="electron" fill={strokecolor} cx={A70cos * rad3} cy={-A70sin * rad3} {r} />
        {/if}
        {#if num > 28}
          <circle class="electron" fill={strokecolor} cx={-A70cos * rad3} cy={A70sin * rad3} {r} />
          <circle class="electron" fill={strokecolor} cx={A70cos * rad3} cy={A70sin * rad3} {r} />
        {/if}
      </g>
    {/if}

    {#if num > 18}
      <g class="four">
        <circle r={rad4} fill="none" stroke={strokecolor} stroke-width={ringSize} />
        <circle class="electron" fill={strokecolor} cx={-A0sin * rad4} cy={-A0cos * rad4} {r} />
        {#if num > 19 && num != 24 && num != 29}
          <circle class="electron" fill={strokecolor} cx={-A0sin * rad4} cy={A0cos * rad4} {r} />
        {/if}
        {#if num > 30}
          <circle class="electron" fill={strokecolor} cx={-A90sin * rad4} cy={A90cos * rad4} {r} />
        {/if}
        {#if num > 31}
          <circle class="electron" fill={strokecolor} cx={A90sin * rad4} cy={A90cos * rad4} {r} />
        {/if}
        {#if num > 32}
          <circle class="electron" fill={strokecolor} cx={-A45 * rad4} cy={-A45 * rad4} {r} />
        {/if}
        {#if num > 33}
          <circle class="electron" fill={strokecolor} cx={A45 * rad4} cy={-A45 * rad4} {r} />
        {/if}
        {#if num > 34}
          <circle class="electron" fill={strokecolor} cx={-A45 * rad4} cy={A45 * rad4} {r} />
        {/if}
        {#if num > 35}
          <circle class="electron" fill={strokecolor} cx={A45 * rad4} cy={A45 * rad4} {r} />
        {/if}
        {#if num > 38}
          <circle class="electron" fill={strokecolor} cx={-A22cos * rad4} cy={-A22sin * rad4} {r} />
        {/if}
        {#if num > 39}
          <circle class="electron" fill={strokecolor} cx={A22cos * rad4} cy={-A22sin * rad4} {r} />
        {/if}
        {#if num > 40}
          <circle class="electron" fill={strokecolor} cx={A22cos * rad4} cy={A22sin * rad4} {r} />
          <circle class="electron" fill={strokecolor} cx={-A22cos * rad4} cy={A22sin * rad4} {r} />
        {/if}
        {#if num > 41}
          <circle class="electron" fill={strokecolor} cx={-A22sin * rad4} cy={-A22cos * rad4} {r} />
        {/if}
        {#if num > 43}
          <circle class="electron" fill={strokecolor} cx={A22sin * rad4} cy={-A22cos * rad4} {r} />
          <circle class="electron" fill={strokecolor} cx={-A22sin * rad4} cy={A22cos * rad4} {r} />
        {/if}
        {#if num > 44}
          <circle class="electron" fill={strokecolor} cx={A22sin * rad4} cy={A22cos * rad4} {r} />
        {/if}
        {#if num > 45}
          <circle class="electron" fill={strokecolor} cx={-A11cos * rad4} cy={-A11sin * rad4} {r} />
          <circle class="electron" fill={strokecolor} cx={A11cos * rad4} cy={-A11sin * rad4} {r} />
        {/if}
        {#if num > 57}
          <circle class="electron" fill={strokecolor} cx={-A11sin * rad4} cy={A11cos * rad4} {r} />
        {/if}
        {#if num > 58}
          <circle class="electron" fill={strokecolor} cx={A33cos * rad4} cy={A33sin * rad4} {r} />
          <circle class="electron" fill={strokecolor} cx={-A11sin * rad4} cy={-A11cos * rad4} {r} />
        {/if}
        {#if num > 59}
          <circle class="electron" fill={strokecolor} cx={A33sin * rad4} cy={-A33cos * rad4} {r} />
        {/if}
        {#if num > 60}
          <circle class="electron" fill={strokecolor} cx={-A33cos * rad4} cy={A33sin * rad4} {r} />
        {/if}
        {#if num > 61}
          <circle class="electron" fill={strokecolor} cx={-A33sin * rad4} cy={-A33cos * rad4} {r} />
        {/if}
        {#if num > 62}
          <circle class="electron" fill={strokecolor} cx={A11sin * rad4} cy={A11cos * rad4} {r} />
        {/if}
        {#if num > 64}
          <circle class="electron" fill={strokecolor} cx={-A11cos * rad4} cy={A11sin * rad4} {r} />
          <circle class="electron" fill={strokecolor} cx={A11cos * rad4} cy={A11sin * rad4} {r} />
        {/if}
        {#if num > 65}
          <circle class="electron" fill={strokecolor} cx={A11sin * rad4} cy={-A11cos * rad4} {r} />
        {/if}
        {#if num > 66}
          <circle class="electron" fill={strokecolor} cx={-A33cos * rad4} cy={-A33sin * rad4} {r} />
        {/if}
        {#if num > 67}
          <circle class="electron" fill={strokecolor} cx={A33sin * rad4} cy={A33cos * rad4} {r} />
        {/if}
        {#if num > 68}
          <circle class="electron" fill={strokecolor} cx={A33cos * rad4} cy={-A33sin * rad4} {r} />
        {/if}
        {#if num > 69}
          <circle class="electron" fill={strokecolor} cx={-A33sin * rad4} cy={A33cos * rad4} {r} />
        {/if}
      </g>
    {/if}

    {#if num > 36 && num != 46}
      <g class="five">
        <circle r={rad5} fill="none" stroke={strokecolor} stroke-width={ringSize} />
        <circle class="electron" fill={strokecolor} cx={-A0sin * rad5} cy={-A0cos * rad5} {r} />
        {#if num > 37 && num != 41 && num != 42 && num != 44 && num != 45 && num != 46 && num != 47}
          <circle class="electron" fill={strokecolor} cx={A0sin * rad5} cy={A0cos * rad5} {r} />
        {/if}
        {#if num > 48}
          <circle class="electron" fill={strokecolor} cx={-A90sin * rad5} cy={A90cos * rad5} {r} />
        {/if}
        {#if num > 49}
          <circle class="electron" fill={strokecolor} cx={A90sin * rad5} cy={A90cos * rad5} {r} />
        {/if}
        {#if num > 50}
          <circle class="electron" fill={strokecolor} cx={-A45 * rad5} cy={-A45 * rad5} {r} />
        {/if}
        {#if num > 51}
          <circle class="electron" fill={strokecolor} cx={A45 * rad5} cy={-A45 * rad5} {r} />
        {/if}
        {#if num > 52}
          <circle class="electron" fill={strokecolor} cx={-A45 * rad5} cy={A45 * rad5} {r} />
        {/if}
        {#if num > 53}
          <circle class="electron" fill={strokecolor} cx={A45 * rad5} cy={A45 * rad5} {r} />
        {/if}
        {#if num > 56 && num != 59 && num != 60 && num != 61 && num != 62 && num != 63 && num != 65 && num != 66 && num != 67 && num != 68 && num != 69 && num != 70}
          <circle class="electron" fill={strokecolor} cx={-A22cos * rad5} cy={-A22sin * rad5} {r} />
        {/if}
        {#if num > 71}
          <circle class="electron" fill={strokecolor} cx={A22cos * rad5} cy={-A22sin * rad5} {r} />
        {/if}
        {#if num > 72}
          <circle class="electron" fill={strokecolor} cx={A22cos * rad5} cy={A22sin * rad5} {r} />
        {/if}
        {#if num > 73}
          <circle class="electron" fill={strokecolor} cx={-A22cos * rad5} cy={A22sin * rad5} {r} />
        {/if}
        {#if num > 74}
          <circle class="electron" fill={strokecolor} cx={-A22sin * rad5} cy={-A22cos * rad5} {r} />
        {/if}
        {#if num > 75}
          <circle class="electron" fill={strokecolor} cx={A22sin * rad5} cy={-A22cos * rad5} {r} />
        {/if}
        {#if num > 76}
          <circle class="electron" fill={strokecolor} cx={-A22sin * rad5} cy={A22cos * rad5} {r} />
        {/if}
        {#if num > 77}
          <circle class="electron" fill={strokecolor} cx={A22sin * rad5} cy={A22cos * rad5} {r} />
          <circle class="electron" fill={strokecolor} cx={-A11cos * rad5} cy={-A11sin * rad5} {r} />
        {/if}
        {#if num > 78}
          <circle class="electron" fill={strokecolor} cx={A11cos * rad5} cy={-A11sin * rad5} {r} />
        {/if}
        {#if num > 90}
          <circle class="electron" fill={strokecolor} cx={-A11sin * rad5} cy={A11cos * rad5} {r} />
          <circle class="electron" fill={strokecolor} cx={A33cos * rad5} cy={A33sin * rad5} {r} />
        {/if}
        {#if num > 91}
          <circle class="electron" fill={strokecolor} cx={-A11sin * rad5} cy={-A11cos * rad5} {r} />
        {/if}
        {#if num > 92}
          <circle class="electron" fill={strokecolor} cx={A33sin * rad5} cy={-A33cos * rad5} {r} />
        {/if}
        {#if num > 93}
          <circle class="electron" fill={strokecolor} cx={-A33cos * rad5} cy={A33sin * rad5} {r} />
          <circle class="electron" fill={strokecolor} cx={-A33sin * rad5} cy={-A33cos * rad5} {r} />
        {/if}
        {#if num > 94}
          <circle class="electron" fill={strokecolor} cx={A11sin * rad5} cy={A11cos * rad5} {r} />
        {/if}
        {#if num > 96}
          <circle class="electron" fill={strokecolor} cx={-A11cos * rad5} cy={A11sin * rad5} {r} />
        {/if}
        {#if num > 96}
          <circle class="electron" fill={strokecolor} cx={A11cos * rad5} cy={A11sin * rad5} {r} />
        {/if}
        {#if num > 97}
          <circle class="electron" fill={strokecolor} cx={A11sin * rad5} cy={-A11cos * rad5} {r} />
        {/if}
        {#if num > 98}
          <circle class="electron" fill={strokecolor} cx={-A33cos * rad5} cy={-A33sin * rad5} {r} />
        {/if}
        {#if num > 99}
          <circle class="electron" fill={strokecolor} cx={A33sin * rad5} cy={A33cos * rad5} {r} />
        {/if}
        {#if num > 100}
          <circle class="electron" fill={strokecolor} cx={A33cos * rad5} cy={-A33sin * rad5} {r} />
        {/if}
        {#if num > 101}
          <circle class="electron" fill={strokecolor} cx={-A33sin * rad5} cy={A33cos * rad5} {r} />
        {/if}
      </g>
    {/if}

    {#if num > 54}
      <g class="six">
        <circle r={rad6} fill="none" stroke={strokecolor} stroke-width={ringSize} />
        <circle class="electron" fill={strokecolor} cx={-A0sin * rad6} cy={-A0cos * rad6} {r} />
        {#if num > 55 && num != 78 && num != 79}
          <circle class="electron" fill={strokecolor} cx={A0sin * rad6} cy={A0cos * rad6} {r} />
        {/if}
        {#if num > 80}
          <circle class="electron" fill={strokecolor} cx={-A10cos * rad6} cy={-A10sin * rad6} {r} />
        {/if}
        {#if num > 81}
          <circle class="electron" fill={strokecolor} cx={A10cos * rad6} cy={-A10sin * rad6} {r} />
        {/if}
        {#if num > 82}
          <circle class="electron" fill={strokecolor} cx={-A30cos * rad6} cy={A30sin * rad6} {r} />
        {/if}
        {#if num > 83}
          <circle class="electron" fill={strokecolor} cx={A30cos * rad6} cy={A30sin * rad6} {r} />
        {/if}
        {#if num > 84}
          <circle class="electron" fill={strokecolor} cx={-A50cos * rad6} cy={-A50sin * rad6} {r} />
        {/if}
        {#if num > 85}
          <circle class="electron" fill={strokecolor} cx={A50cos * rad6} cy={-A50sin * rad6} {r} />
        {/if}
        {#if num > 88 && num != 94 && num != 95 && num != 97 && num != 98 && num != 99 && num != 100 && num != 101 && num != 102 && num != 103}
          <circle class="electron" fill={strokecolor} cx={-A50cos * rad6} cy={A50sin * rad6} {r} />
        {/if}
        {#if num > 89 && num != 91 && num != 92 && num != 93 && num != 94 && num != 95 && num != 96 && num != 97 && num != 98 && num != 99 && num != 100 && num != 101 && num != 102 && num != 103}
          <circle class="electron" fill={strokecolor} cx={A50cos * rad6} cy={A50sin * rad6} {r} />
        {/if}
        {#if num > 104}
          <circle class="electron" fill={strokecolor} cx={-A30cos * rad6} cy={-A30sin * rad6} {r} />
        {/if}
        {#if num > 105}
          <circle class="electron" fill={strokecolor} cx={A30cos * rad6} cy={-A30sin * rad6} {r} />
        {/if}
        {#if num > 106}
          <circle class="electron" fill={strokecolor} cx={-A10cos * rad6} cy={A10sin * rad6} {r} />
        {/if}
        {#if num > 107}
          <circle class="electron" fill={strokecolor} cx={A10cos * rad6} cy={A10sin * rad6} {r} />
        {/if}
        {#if num > 108}
          <circle class="electron" fill={strokecolor} cx={-A70cos * rad6} cy={-A70sin * rad6} {r} />
        {/if}
        {#if num > 109}
          <circle class="electron" fill={strokecolor} cx={A70cos * rad6} cy={-A70sin * rad6} {r} />
        {/if}
        {#if num > 110}
          <circle class="electron" fill={strokecolor} cx={-A70cos * rad6} cy={A70sin * rad6} {r} />
        {/if}
        {#if num > 111}
          <circle class="electron" fill={strokecolor} cx={A70cos * rad6} cy={A70sin * rad6} {r} />
        {/if}
      </g>
    {/if}

    {#if num > 86}
      <g class="seven">
        <circle r={rad7} fill="none" stroke={strokecolor} stroke-width={ringSize} />
        <circle class="electron" fill={strokecolor} cx={-A0sin * rad7} cy={-A0cos * rad7} {r} />
        {#if num > 87}
          <circle class="electron" fill={strokecolor} cx={A0sin * rad7} cy={A0cos * rad7} {r} />
        {/if}
        {#if num > 102 && num != 104 && num != 105 && num != 106 && num != 107 && num != 108 && num != 109 && num != 110 && num != 111 && num != 112}
          <circle class="electron" fill={strokecolor} cx={-A90sin * rad7} cy={A90cos * rad7} {r} />
        {/if}
        {#if num > 113}
          <circle class="electron" fill={strokecolor} cx={A90sin * rad7} cy={A90cos * rad7} {r} />
        {/if}
        {#if num > 114}
          <circle class="electron" fill={strokecolor} cx={-A45 * rad7} cy={-A45 * rad7} {r} />
        {/if}
        {#if num > 115}
          <circle class="electron" fill={strokecolor} cx={A45 * rad7} cy={-A45 * rad7} {r} />
        {/if}
        {#if num > 116}
          <circle class="electron" fill={strokecolor} cx={-A45 * rad7} cy={A45 * rad7} {r} />
        {/if}
        {#if num > 117}
          <circle class="electron" fill={strokecolor} cx={A45 * rad7} cy={A45 * rad7} {r} />
        {/if}
      </g>
    {/if}
  </g>
</svg>
