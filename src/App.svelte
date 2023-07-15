<script lang="ts">
  let height: number, weight: number
  $: bmi = Math.floor((weight / (height / 100) ** 2) * 100) / 100
</script>

<main class="max-w-2xl mx-auto p-8">
  <h1 class="text-4xl font-bold text-center mb-4">BMI Calc</h1>
  <div class="form-control mb-6">
    <div class="relative my-4">
      <input placeholder="Height" bind:value={height} class="w-full input input-bordered" />
      <div class="absolute bottom-0 right-0 p-3">cm</div>
    </div>
    <div class="relative my-4">
      <input placeholder="Weight" bind:value={weight} class="w-full input input-bordered" />
      <div class="absolute bottom-0 right-0 p-3">kg</div>
    </div>
  </div>
  {#if bmi}
    {#if bmi < 18.5}
      <div class="bg-blue-300 text-blue-800 rounded-box p-4 h-40 flex justify-center items-center text-2xl">
        <div>{bmi}</div>
      </div>
    {:else if bmi < 25}
      <div class="bg-green-300 text-green-800 rounded-box p-4 h-40 flex justify-center items-center text-2xl font-bold">
        <div>{bmi}</div>
      </div>
    {:else if bmi < 30}
      <div class="bg-red-300 text-red-800 rounded-box p-4 h-40 flex justify-center items-center text-2xl font-bold">
        <div>{bmi}</div>
      </div>
    {:else if bmi < 35}
      <div class="bg-red-500 text-red-100 rounded-box p-4 h-40 flex justify-center items-center text-2xl font-bold">
        <div>{bmi}</div>
      </div>
    {:else if bmi < 40}
      <div class="bg-red-950 text-red-100 rounded-box p-4 h-40 flex justify-center items-center text-2xl font-bold">
        <div>{bmi}</div>
      </div>
    {:else}
      <div class="bg-purple-950 text-purple-100 rounded-box p-4 h-40 flex justify-center items-center text-2xl font-bold">
        <div>{bmi}</div>
      </div>
    {/if}
  {/if}
</main>
