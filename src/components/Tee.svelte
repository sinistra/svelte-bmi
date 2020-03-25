<script>
  export let bmr = 1800;
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
    font-size: small;
  }
</style>

<div>
  {#each levels as level}
    <div class="inline">
      <div>{level.description}</div>
      <div>{bmr * level.value}</div>
    </div>
  {/each}
</div>
