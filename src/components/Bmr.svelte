<script>
  export let weight = 0;
  export let height = 0;
  export let age = 20;
  export let gender = "m";

  // BMR male = 66.5 + ( 13.75 × weight in kg ) + ( 5.003 × height in cm ) – ( 6.755 × age in years )
  // BMR female = 655.1 + ( 9.563 × weight in kg ) + ( 1.850 × height in cm ) – ( 4.676 × age in years )

  // BMR revised by Mifflin and St Jeor in 1990
  // Men	BMR = (10 × weight in kg) + (6.25 × height in cm) - (5 × age in years) + 5
  // Women	BMR = (10 × weight in kg) + (6.25 × height in cm) - (5 × age in years) - 161

  $: baseBMR = 10 * weight + 6.25 * height - 5 * age;
  $: bmr = gender == "m" ? baseBMR + 5 : baseBMR - 161;
</script>

<div>
  <h5>BMR</h5>
  <div>{bmr}</div>
</div>
