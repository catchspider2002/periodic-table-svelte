<script>
  let options = [
    { id: "en", value: "English" },
    { id: "fr", value: "French" },
    { id: "es", value: "Espanol" },
    { id: "zh", value: "Chinese" },
  ];

  let selected = "en";

  function navigate(val) {
    console.log(val);
    window.location.href = "./" + val;
  }
</script>

<style>
  
select {
  margin-top: 5px;
}
</style>

<select bind:value={selected} on:change={() => navigate(selected)}>
  {#each options as option}
    <option value={option.id}>{option.value}</option>
  {/each}
</select>
