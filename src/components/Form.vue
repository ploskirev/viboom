<template>
  <form action="#" @submit.prevent>
    <label>
      <p class="form-description">
        Введите сумму, чтобы увидеть прогноз по&nbsp;подписчикам и&nbsp;просмотрам
      </p>
      <div class="input-block">
        <svg 
          width="14" 
          height="22" 
          viewBox="0 0 14 22" 
          fill="none" 
          xmlns="http://www.w3.org/2000/svg"
        >
          <path 
            fill-rule="evenodd" 
            clip-rule="evenodd" 
            d="M5.8354 0.617224C4.5432 0.535157 3.5585 1.58963 3.55839 2.78394L3.55765 10.7565L1.87783 10.7563C1.21508 10.7562 0.677758 11.2934 0.677673 11.9561C0.677589 12.6188 1.21478 13.1562 1.87752 13.1563L3.55764 13.1565L3.5571 14.561H1.89325C1.23051 14.561 0.69325 15.0983 0.69325 15.761C0.69325 16.4237 1.23051 16.961 1.89325 16.961H3.55617L3.55492 20.1848C3.55467 20.8476 4.09172 21.385 4.75446 21.3853C5.4172 21.3855 5.95467 20.8485 5.95492 20.1858L5.95617 16.961H9.7683C10.431 16.961 10.9683 16.4237 10.9683 15.761C10.9683 15.0983 10.431 14.561 9.7683 14.561H5.9571L5.95765 13.127C7.85051 12.9824 9.55759 12.3794 10.8615 11.3993C12.4599 10.198 13.459 8.4099 13.3126 6.31984C13.1895 4.56382 12.3378 3.15398 10.9613 2.1838C9.62354 1.24091 7.8428 0.744714 5.8354 0.617224ZM5.95858 10.7183C7.37844 10.5807 8.569 10.1201 9.41956 9.4808C10.4776 8.68558 10.999 7.63715 10.9184 6.48757C10.8483 5.48671 10.3953 4.72107 9.57869 4.14551C8.76907 3.57488 7.56034 3.16825 5.95836 3.03274L5.95836 3.09785C5.96045 3.12688 5.96151 3.15619 5.96149 3.18575L5.95858 10.7183Z" fill="#7045C4"
          />
        </svg>
        <input type="number" v-model="sum" @input="onInput(sum)">
        <span>руб.</span>
      </div>
    </label>
  </form>
</template>

<script>
export default {
  name: 'Form',
  props: ['money', 'onInput'],
  data() {
    return {
      sum: this.money
    }
  }
}
</script>

<style lang="scss" scoped>
@import '../assets/styles/variables.scss';

form {
  background-color: $bgForm;
  border-radius: 6px;
  padding: 30px 50px 47px 50px;
  font-family: $mont;
  font-weight: 500;
  font-size: 16px;

  @media (max-width: 1439px) {
    & {
      width: 502px;
      padding: 30px 40px;
    }
  }

  @media (max-width: 959px) {
    & {
      width: 100%;
      padding: 24px 20px 30px 20px;
      font-size: 32px;
      line-height: 42px;
    }
  }

  .form-description {
    width: 358px;
    margin-bottom: 40px;
    font-family: $pt;
    font-size: 20px;
    line-height: 24px;
    color: $primaryText;

    @media (max-width: 1439px) {
      & {
        min-width: 358px;
        width: 95%;
        font-size: 18px;
        line-height: 23px;
      }
    }

    @media (max-width: 959px) {
      & {
        width: 90%;
        min-width: auto;
        margin-bottom: 30px;
        font-size: 16px;
        line-height: 20px;
        letter-spacing: .02em;
      }
    }
  }

  .input-block {
    display: flex;
    justify-content: flex-start;
    align-items: center;

    svg {
      width: 30px;
      height: 30px;
      border-radius: 50%;
      padding: 3px;
      border: 1px solid #7045C4;

      @media (max-width: 959px) {
        width: 26px;
        height: 26px;
        flex-shrink: 0;
      }
    }

    input {
      width: 308px;
      height: 44px;
      border-radius: 6px;
      border: none;
      margin: 0 20px;
      padding: 0 20px;
      font-family: $mont;
      font-weight: 500;
      font-size: 16px;
      letter-spacing: .02em;

      &:focus {
        outline-color: $third;
      }

      @media (max-width: 1439px) {
        & {
          width: 270px;
          font-size: 18px;
        }
      }

      @media (max-width: 959px) {
        & {
          flex-grow: 1;
          flex-basis: 283px;
          height: 40px;
          margin: 0 16px;
          font-size: 15px;
        }
      }
    }

    @media (max-width: 959px) {
      & {
        width: 100%;
        font-size: 15px;
      }
    }
  }
}
</style>
