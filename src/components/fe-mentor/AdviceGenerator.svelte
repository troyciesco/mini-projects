<script lang="ts">
  import { onMount } from "svelte"

  let advice: any
  let isLoading: boolean = false

  const fetchAdvice = async () => {
    isLoading = true
    const response = await fetch("https://api.adviceslip.com/advice")
    const data = await response.json()
    advice = data.slip
    isLoading = false
  }

  onMount(() => {
    fetchAdvice()
  })
</script>

<section>
  <div class="card">
    {#if isLoading}
      <span class="card__id" />
      <p class="card__quote">loading...</p>
    {:else}
      <span class="card__id">Advice #{advice?.id}</span>
      <p class="card__quote">{advice?.advice}</p>
    {/if}
    <img
      class="card__divider"
      src="/fe-mentor/advice-generator/pattern-divider-desktop.svg"
      alt="" />
    <button
      class="card__btn"
      on:click={fetchAdvice}
      ><img
        src="/fe-mentor/advice-generator/icon-dice.svg"
        alt="" />
    </button>
  </div>
</section>

<style lang="scss">
  @import url("https://fonts.googleapis.com/css2?family=Manrope:wght@800&display=swap");

  section {
    margin: 0;
    padding: 0;
    font-family: "Manrope", sans-serif;
    font-weight: 800;
    background: #202733;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .card {
    padding: 3rem;
    border-radius: 15px;
    background: #313a48;
    box-shadow: 30px 50px 80px rgba(0, 0, 0, 0.100202);
    text-align: center;
    position: relative;

    &__id {
      color: #53ffaa;
      margin-bottom: 1.5rem;
      display: block;
      text-transform: uppercase;
      letter-spacing: 4px;
    }

    &__quote {
      color: #cee3e9;
      font-weight: 800;
      font-size: 28px;
      letter-spacing: -0.3px;
      line-height: 38.25px;
      max-width: 65ch;
      margin: 0 auto 2.5rem auto;
    }

    &__divider {
      width: 100%;
      object-fit: contain;
      margin-bottom: 2.5rem;
    }

    &__btn {
      position: absolute;
      // ngl, point of this commit is to account for the fact that
      // i had 35 contributions on a private gitlab today and i wanna keep the
      // graph on github going
      bottom: -2rem;
      left: calc(50% - 32px);
      border: none;
      border-radius: 50%;
      background: #53ffaa;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 20px;
      cursor: pointer;
      transition: box-shadow 0.2s ease;

      &:hover {
        box-shadow: 0px 0px 40px #53ffaa;
      }
    }
  }
</style>
