<template>
  <div class="card-body" :class="{ 'content-hidden': visible === false }">
    <div class="card-top">
      <inline-svg class="card-logo" :src="require('@/assets/svg/patricia-logo.svg')"></inline-svg>
      <button class="visibility-toggle" @click="toggleVisibility">
        <inline-svg class="visbility-toggle-icon" v-show="visible === false" :src="require('@/assets/svg/eye-close.svg')"></inline-svg>
        <inline-svg class="visbility-toggle-icon" v-show="visible === true" :src="require('@/assets/svg/eye-open.svg')"></inline-svg>
      </button>
    </div>

    <div class="card-middle">
      <p class="card-number">
        {{ visible ? '9784' : '••••' }}
      </p>
      <p class="card-number">
        {{ visible ? '9784' : '••••' }}
      </p>
      <p class="card-number">
        {{ visible ? '9784' : '••••' }}
      </p>
      <p class="card-number">
        9784
      </p>
    </div>

    <div class="card-bottom">
      <p class="card-holder-name">Cardholder Name</p>
      <div class="card-date-cvv">
        <div class="card-date">
          <span class="card-date-text">
            VALID
            <br />
            THRU
          </span>
          <span class="card-date-number">
            10/12
          </span>
        </div>
        <div class="card-cvv">
          <span class="card-cvv-text">
            CVV
          </span>
          <p class="card-cvv-number">
            {{ visible ? '455' : '•••' }}
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import InlineSvg from 'vue-inline-svg';
export default {
  name: 'Card',
  data() {
    return {
      visible: false,
    };
  },
  components: {
    InlineSvg,
  },
  methods: {
    toggleVisibility() {
      this.visible = !this.visible;
    },
  },
};
</script>

<style lang="scss" scoped>
.card-body {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  font-family: 'Graphik';
  background-color: $p-black;
  background-image: url('../assets/images/patricia-icon-small.png');
  background-repeat: no-repeat;
  background-size: contain;
  color: $p-smoke;
  border-radius: 20px;
  padding: 12px 20px;
  height: 200px;
  max-width: 327px;
  margin: auto;

  &.content-hidden {
    background-image: url('../assets/images/patricia-icon-large.png');
  }
}

.card-top {
  display: flex;
  justify-content: space-between;
  padding-top: 10px;
}
.card-logo {
  width: 70px;
}
.visibility-toggle {
  display: inline-block;
  background: transparent;
  border: none;
  transition: opacity 0.3s;
  cursor: pointer;

  &:focus {
    outline: none;
    opacity: 0.8;
  }
  &:hover {
    opacity: 0.8;
  }
}
.visbility-toggle-icon {
  height: 24px;
  width: 23px;
}

.card-middle {
  display: flex;
  justify-content: space-between;
}

.card-number {
  display: inline-block;
  font-size: 0.85rem;
  letter-spacing: 2px;
  color: $p-smoke;
}

.card-holder-name {
  font-size: 0.61rem;
}

.card-bottom {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.card-date-cvv {
  display: flex;
  align-items: center;
}

.card-date {
  display: flex;
  align-items: center;
  margin-right: 15px;
  &-text {
    color: $p-smoke-dark;
    display: inline-block;
    margin-right: 7px;
    font-size: 0.25rem;
  }
  &-number {
    font-size: 0.7rem;
  }
}

.card-cvv {
  display: flex;
  align-items: center;

  &-text {
    color: $p-smoke-dark;
    display: inline-block;
    margin-right: 7px;
    font-size: 0.25rem;
  }
  &-number {
    font-size: 0.7rem;
    width: 25px;
  }
}

@include for-tablet-portrait-up {
  .card-body {
    border-radius: 20px;
    padding: 20px 40px;
    height: 305px;
    max-width: 499px;
  }
  .card-logo {
    width: 96px;
  }
  .visbility-toggle-icon {
    height: 28px;
    width: 27px;
  }
  .card-number {
    font-size: 1.3rem;
    letter-spacing: 4px;
  }
  .card-holder-name {
    font-size: 0.8rem;
  }
  .card-date {
    display: flex;
    align-items: center;
    margin-right: 30px;
    &-text {
      color: $p-smoke-dark;
      display: inline-block;
      margin-right: 12px;
      font-size: 0.42rem;
    }
    &-number {
      font-size: 0.97rem;
    }
  }
  .card-cvv {
    display: flex;
    align-items: center;

    &-text {
      color: $p-smoke-dark;
      display: inline-block;
      margin-right: 12px;
      font-size: 0.49rem;
    }
    &-number {
      font-size: 0.97rem;
    }
  }
}
</style>
