<script>
  export let weight = 0;
  export let height = 0;
  // export let age = 20;
  // export let gender = 'm';

  // [weight (kg) / height (cm) / height (cm)] x 10,000
  $: bmi = height ? (weight / height / height) * 10000 : 0;
</script>

<div>
  <h5>BMI</h5>
  <div>{bmi}</div>
</div>
