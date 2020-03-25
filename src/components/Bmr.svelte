<script>
  export let weight = 0;
  export let height = 0;
  export let age = 0;
  export let gender = "m";

  // BMR male = 66.5 + ( 13.75 × weight in kg ) + ( 5.003 × height in cm ) – ( 6.755 × age in years )
  // BMR female = 655.1 + ( 9.563 × weight in kg ) + ( 1.850 × height in cm ) – ( 4.676 × age in years )

  // BMR revised by Mifflin and St Jeor in 1990
  // Men	BMR = (10 × weight in kg) + (6.25 × height in cm) - (5 × age in years) + 5
  // Women	BMR = (10 × weight in kg) + (6.25 × height in cm) - (5 × age in years) - 161

  $: baseBMR = 10 * weight + 6.25 * height - 5 * age;
  $: bmr = gender == "m" ? baseBMR + 5 : baseBMR - 161;
  $: isValid = weight > 0 && height > 0 && age > 0;

  let levels = [
    { description: "sedentary (little or no exercise)", value: 1.2 },
    {
      description: "lightly active (light exercise/sports 1-3 days/week)",
      value: 1.375
    },
    {
      description: "moderately active (moderate exercise/sports 3-5 days/week)",
      value: 1.55
    },
    {
      description: "very active (hard exercise/sports 6-7 days a week)",
      value: 1.725
    },
    {
      description:
        "extra active (very hard exercise/sports & physical job or 2x training)",
      value: 1.9
    }
  ];
</script>

<style>
  .inline {
    display: flex;
    justify-content: space-between;
  }

  .small {
    font-size: small;
  }
</style>

<div class="inline">
  <h5>BMR</h5>
  {#if isValid}
    <div>{bmr}</div>
  {/if}
</div>

<div>
<h6>Total Energy Expended</h6>
  {#each levels as level}
    <div class="inline small">
      <div>{level.description}</div>
      {#if isValid}
        <div>{(bmr * level.value).toFixed(0)}</div>
      {/if}
    </div>
  {/each}
</div>
