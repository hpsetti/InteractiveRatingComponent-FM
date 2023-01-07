<template>
  <div class="interactive-rating">
    <div v-if="!ratingSubmitted" class="interactive-rating__content">
      <div class="content__icon d-flex justify-center align-items-center">
        <img src="@/assets/images/icon-star.svg" alt="icon-star" />
      </div>
      <div class="content__text-container">
        <h1>How did we do?</h1>
        <div class="text-container__description">
          <p>
            Please let us know how we did with your support request. All
            feedback is appreciated to help us improve our offering!
          </p>
        </div>
        <div
          class="text-container__button-container d-flex justify-space-between align-items-center"
        >
          <button
            v-for="(numb, index) in '12345'"
            :key="index"
            @click="(e) => ratingbtnClick(e)"
          >
            {{ numb }}
          </button>
        </div>
        <div class="text-container__submit-container">
          <button @click="submitBtnClick" :disabled="!ratingNumber">
            Submit
          </button>
        </div>
      </div>
    </div>
    <div class="thank-you" v-else>
      <div class="thank-you__img-container">
        <img src="@/assets/images/illustration-thank-you.svg" />
      </div>
      <div class="thank-you__rating-container d-flex justify-center">
        <p class="thank-you__rating d-flex justify-center align-items-center">
          You selected {{ ratingNumber }} out of 5
        </p>
      </div>
      <div class="thank-you__container">
        <h1>Thank You!</h1>
        <p class="thank-you__message">
          We appreciate you taking the time to give a rating. If you ever need
          more support, don't hesitate to get in touch!
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "InteractiveRating",
  data() {
    return {
      ratingNumber: null,
      ratingSubmitted: false,
    };
  },
  methods: {
    ratingbtnClick(e) {
      this.ratingNumber = Number(e.target.innerText);
    },
    submitBtnClick() {
      console.log(this.ratingNumber);
      this.ratingSubmitted = true;
    },
  },
};
</script>

<style lang="css">
.interactive-rating {
  height: 420px;
  width: 415px;
  background: linear-gradient(
    180deg,
    rgba(34, 41, 51, 1) 11%,
    rgba(28, 35, 45, 1) 41%
  );
  border-radius: 30px;
}

.interactive-rating__content {
  padding: 30px;
  height: 100%;
}

.content__icon {
  height: 52px;
  width: 52px;
  border-radius: 50%;
  background-color: #253037;
}

.content__text-container {
  margin-top: 35px;
}

.content__text-container h1 {
  color: var(--white);
  font-size: 25px;
  line-height: normal;
}

.text-container__description {
  margin-top: 20px;
  margin-bottom: 30px;
}

.text-container__description p {
  color: var(--light-grey);
}

.text-container__button-container button {
  width: 52px;
  height: 52px;
  border-radius: 50%;
  background-color: #253037;
  border: none;
  color: var(--medium-grey);
}

.text-container__button-container button:hover {
  background-color: var(--light-grey);
  color: var(--white);
  cursor: pointer;
}

.text-container__button-container button:focus,
.text-container__button-container button:active {
  background-color: var(--primary);
  color: var(--white);
  cursor: pointer;
}

.text-container__submit-container {
  margin-top: 30px;
  height: 45px;
  width: 100%;
}

.text-container__submit-container button {
  height: 100%;
  width: 100%;
  border-radius: 50px;
  border: none;
  background-color: var(--primary);
  font-size: 12px;
  color: var(--white);
  letter-spacing: 3px;
  text-transform: uppercase;
}

.text-container__submit-container button:focus,
.text-container__submit-container button:active,
.text-container__submit-container button:hover {
  color: var(--primary);
  background-color: var(--white);
  cursor: pointer;
}

.text-container__submit-container button:disabled,
.text-container__submit-container button[disabled] {
  border: 1px solid #999999;
  background-color: #cccccc;
  color: #666666;
  cursor: not-allowed;
}

.thank-you {
  height: 100%;
}

.thank-you__img-container {
  margin-top: 45px;
}

.thank-you__img-container img {
  margin-left: auto;
  margin-right: auto;
}

.thank-you__rating-container {
  display: flex;
  justify-content: center;
}

.thank-you__rating {
  text-align: center;
  margin-top: 30px;
  height: 32px;
  min-width: 188px;
  background-color: #272f3b;
  border-radius: 50px;
  display: flex;
  justify-content: center;
  align-items: center;
  color: var(--primary);
}

.thank-you__container {
  text-align: center;
  margin-left: 35px;
  margin-right: 35px;
  color: var(--light-grey);
}

.thank-you__container h1 {
  margin-top: 35px;
  margin-bottom: 15px;
  color: var(--white);
}

@media (max-width: 600px) {
  .interactive-rating {
    height: 360px;
    width: 330px;
  }

  .content__text-container {
    margin-top: 20px;
  }

  .interactive-rating__content {
    padding: 25px;
  }

  .content__icon {
    height: 45px;
    width: 45px;
  }

  .content__text-container h1 {
    font-size: 19px;
  }

  .text-container__description p {
    font-size: 14px;
  }

  .text-container__button-container button {
    height: 45px;
    width: 45px;
  }

  .text-container__submit-container {
    margin-top: 20px;
  }

  .thank-you__img-container {
    margin-top: 30px;
  }

  .thank-you__img-container img {
    height: 100px;
    width: 150px;
  }

  .thank-you__rating {
    margin-top: 25px;
    font-size: 14px;
  }

  .thank-you__container h1 {
    margin-top: 30px;
    font-size: 19px;
  }

  .thank-you__message {
    font-size: 14px;
  }
}
</style>
