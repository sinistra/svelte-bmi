<script>
  export let weight = 0;
  export let height = 0;
  // export let age = 20;
  // export let gender = 'm';

  // [weight (kg) / height (cm) / height (cm)] x 10,000
  $: bmi = height ? (weight / height / height) * 10000 : 0;
  $: targetWeight = (25 / 10000) * height * height;
  $: isValid = weight > 0 && height > 0 ? true : false;
</script>

<style>
  .inline {
    display: flex;
    justify-content: space-between;
  }
</style>

<div class="inline">
  <h5>BMI</h5>
  {#if isValid}
    <div>{bmi.toFixed(2)}</div>
  {/if}
</div>
<div class="inline">
  <h5>target weight</h5>
  {#if isValid}
    <div>{targetWeight.toFixed(2)}</div>
  {/if}
</div>
