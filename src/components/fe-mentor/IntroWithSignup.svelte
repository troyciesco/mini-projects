<script lang="ts">
</script>

<main>
  <section style="display: flex;">
    <div class="container">
      <div class="intro">
        <h1 class="intro__title">Learn to code by watching others</h1>
        <p class="intro__description">
          See how experienced developers solve problems in real-time. Watching scripted tutorials is great, but
          understanding how developers think is invaluable.
        </p>
      </div>
      <div class="sign-up">
        <div class="pricing">
          <p><strong>Try it free for 7 days</strong> then $20/mo thereafter</p>
        </div>
        <form action="">
          <input
            type="text"
            name="firstName"
            placeholder="First Name" />
          <input
            type="text"
            name="lastName"
            placeholder="Last Name" />
          <input
            type="email"
            name="email"
            placeholder="Email" />
          <input
            type="password"
            name="password"
            placeholder="Password" />
          <button type="submit">Claim your free trial</button>
          <span class="disclaimer"
            >By clicking the button, you are agreeing to our <a href="/#">Terms and Services</a></span>
        </form>
      </div>
    </div>
  </section>
</main>

<style lang="scss">
  @import url("https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,400;0,500;0,700;1,400;1,500;1,700&display=swap");

  * {
    font-family: "Poppins", sans-serif;
  }

  main {
    background-color: #ff7979;
    background-image: url("/fe-mentor/intro-with-signup/bg-intro-mobile.png");
    min-height: 100vh;
  }

  .container {
    max-width: 1158px;
    padding: 0 24px;
    padding-top: 88px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 1fr;
    justify-content: center;
    align-items: center;
    gap: 24px;
    @media screen and (min-width: 654px) {
      grid-template-columns: 1fr 1fr;
    }
  }
  .intro {
    color: #ffffff;

    &__title {
      font-size: 28px;
      font-weight: 700;
      text-align: center;
      margin-bottom: 24px;
      letter-spacing: -0.5px;
      line-height: 55px;
      @media screen and (min-width: 654px) {
        text-align: left;
        font-size: 50px;
      }
    }

    &__description {
      font-weight: 500;
      text-align: center;
      @media screen and (min-width: 654px) {
        text-align: left;
      }
    }
  }

  .sign-up {
    min-width: 327px;
  }

  .pricing {
    color: #ffffff;
    background-color: #5e54a4;
    padding: 1rem;
    border-radius: 8px;
    text-align: center;
    margin-bottom: 1.5rem;
  }

  form {
    display: flex;
    flex-direction: column;
    background-color: #ffffff;
    padding: 40px;
    border-radius: 8px;
  }

  input {
    padding: 16px 32px;
    border-radius: 8px;
    margin-bottom: 20px;
    border: 1px solid #dedede;
  }

  button {
    background-color: #38cc8b;
    color: #ffffff;
    padding: 16px;
    border: 1px solid #38cc8b;
    border-radius: 8px;
    text-transform: uppercase;
    font-weight: 700;
    margin-bottom: 8px;
  }

  .disclaimer {
    font-size: 11px;
    color: #bab7d4;
    text-align: center;
    & a {
      text-decoration: none;
      font-weight: 700;
      color: #ff7979;
    }
  }
</style>
