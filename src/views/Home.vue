<template>
  <div class="page-wrapper">
    <div class="card-wrapper">
      <div class="card-section sedans-card">
        <img class="car-icon" src="@/assets/img/icon-sedans.svg" alt="Sedans" />
        <p class="card-title">Sedans</p>
        <p class="card-content">
          Choose a sedan for its affordability and excellent fuel economy. Ideal
          for cruising in the city or on your next road trip.
        </p>

        <a class="card-link" href="#">Learn more</a>
      </div>

      <div class="card-section suvs-card">
        <img class="car-icon" src="@/assets/img/icon-suvs.svg" alt="SUVs" />
        <p class="card-title">SUVs</p>
        <p class="card-content">
          Take an SUV for its spacious interior, power, and versatility. Perfect
          for your next family vacation and off-road adventures.
        </p>

        <a class="card-link" href="#">Learn more</a>
      </div>

      <div class="card-section luxury-card">
        <img class="car-icon" src="@/assets/img/icon-luxury.svg" alt="Luxury" />
        <p class="card-title">Luxury</p>

        <p class="card-content">
          Cruise in the best car brands without the bloated prices. Enjoy the
          enhanced comfort of a luxury rental and arrive in style.
        </p>

        <a class="card-link" href="#">Learn more</a>
      </div>
    </div>
  </div>
</template>

<script>
import { mapState } from 'vuex'

export default {
  head() {
    return {
      title: {
        inner: 'Home'
      },
      meta: [
        {
          name: 'description',
          content: `${this.appTitle} home page`,
          id: 'desc'
        }
      ]
    }
  },
  computed: mapState('app', ['appTitle'])
}
</script>

<style lang="scss" scoped>
@import '@/theme/variables.scss';

.page-wrapper {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.card-wrapper {
  display: flex;

  @media (max-width: 840px) {
    flex-direction: column;
  }
}

.card-section {
  display: flex;
  flex-direction: column;
  padding: 48px 47.5px;

  &.sedans-card {
    border-radius: 8px 0 0 8px;
    background: $primaryColor1;

    @media (max-width: 840px) {
      border-radius: 8px 8px 0 0;
    }

    .card-link {
      color: $primaryColor1;
    }
  }

  &.suvs-card {
    background: $primaryColor2;

    .card-link {
      color: $primaryColor2;
    }
  }

  &.luxury-card {
    border-radius: 0 8px 8px 0;
    background: $primaryColor3;

    @media (max-width: 840px) {
      border-radius: 0 0 8px 8px;
    }

    .card-link {
      color: $primaryColor3;
    }
  }

  img {
    align-self: flex-start;
  }

  .card-title {
    margin: 35px 0 25px;
    font-family: $textFont2;
    font-style: normal;
    font-weight: bold;
    font-size: 40px;
    line-height: 48px;
    text-transform: uppercase;
    color: $neutralColor2;
  }

  .card-content,
  .card-link {
    font-family: $textFont1;
    font-weight: normal;
    font-size: 15px;
    line-height: 25px;
    color: $neutralColor1;
  }

  .card-content {
    margin-bottom: 83px;
    color: $neutralColor1;

    @media (max-width: 840px) {
      margin-bottom: 25px;
    }
  }

  .card-link {
    width: fit-content;
    margin-top: auto;
    padding: 11px 31.5px 12px;
    background: $neutralColor2;
    border-radius: 25px;
    border: 2px solid $neutralColor2;
    transition: all .3s ease-in-out;

    &:hover {
      background: transparent;
      color: $neutralColor2;
    }
  }
}
</style>
