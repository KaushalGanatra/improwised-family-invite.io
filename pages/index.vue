<template>
  <div class="background">
    <div class="quiz-container">
      <div class="modal" v-if="counter === 0">
        <div class="modal-dialog" role="document">
          <div class="modal-content custom-modal">
            <div class="modal-header">
              <h5 class="modal-title">Enter Your Name and Open your surprise Box &#127873;</h5>
            </div>
            <div class="modal-body">
              <input type="text" class="form-control full-width" placeholder="Name Please" v-model="userName">
            </div>
            <div class="modal-footer">
              <button type="button" class="btn btn-primary" @click="nameSubmit">Let's Go</button>
            </div>
          </div>
        </div>
      </div>

      <div v-if="counter === 1" class="center-content text-center">
        <h4><u><b>Are you sure you're {{ userName }}?</b></u></h4>
        <img src="../are-you-sure.png" alt="Are you sure?" class="img-thumbnail transparent-bg">
        <button type="button" class="btn btn-warning full-width-button" @click="backToName">No, let me tell you my name honestly</button>
        <button type="button" class="btn btn-success full-width-button" @click="NextFromValidation">Yes, I'm</button>
      </div>

      <div v-if="counter === 2" class="center-content text-center">
        <div class="welcome-text">
          <h2><u>Welcome {{ userName }} &#127881;</u></h2>
          <h4>Let's first Go on a Quiz about our Improwised Family</h4><hr>
          <ol class="quiz">
            <li>
              <p><b>When was our company established?</b></p>
              <div class="options">
                <label><input type="radio" name="q1" value="a"> 2001</label>
                <label><input type="radio" name="q1" value="b"> 2011</label>
                <label><input type="radio" name="q1" value="c"> 2013</label>
                <label><input type="radio" name="q1" value="d"> 2009</label>
              </div>
            </li>
            <li>
              <p><b>Date when the company was established?</b></p>
              <div class="options">
                <label><input type="radio" name="q2" value="a"> 19</label>
                <label><input type="radio" name="q2" value="b"> 18</label>
                <label><input type="radio" name="q2" value="c"> 23</label>
                <label><input type="radio" name="q2" value="d"> 19</label>
              </div>
            </li>
            <li>
              <p><b>In which month?</b></p>
              <div class="options">
                <label><input type="radio" name="q3" value="a"> Jan</label>
                <label><input type="radio" name="q3" value="b"> Feb</label>
                <label><input type="radio" name="q3" value="c"> May</label>
                <label><input type="radio" name="q3" value="d"> Dec</label>
              </div>
            </li>
          </ol>
          <hr>
          <div v-if="rightANS" class="right-answer">
            <p>But why did you ask that!?</p>
            <NuxtLink to="/padhariye" class="btn btn-secondary">Click to know</NuxtLink>
          </div>

          <!-- Submit Button -->
          <button type="button" class="btn btn-primary" @click="submitQuiz">Submit</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
const counter = ref(0);
const userName = ref('');
const savedUserName = ref('');
const rightANS = ref(false);

const nameSubmit = () => {
  if (userName.value === '') {
    alert("Please enter your name");
    return;
  }
  counter.value++;
};

const backToName = () => {
  userName.value = ""
  counter.value--
}

const NextFromValidation = () => {
  counter.value++
}

const submitQuiz = () => {
  // Get the selected answers
  const answer1 = document.querySelector('input[name="q1"]:checked')?.value;
  const answer2 = document.querySelector('input[name="q2"]:checked')?.value;
  const answer3 = document.querySelector('input[name="q3"]:checked')?.value;
  
  // Check if the answers are correct
  if (answer1 === 'b' && answer2 === 'b' && answer3 === 'c') {
    // Correct answers
    alert('CORRECT');
    rightANS.value = true
    // Redirect to 'padhariye.vue' using nuxt-link
    // Example: window.location.href = '/padhariye.vue';
  } else {
    // Incorrect answers
    alert('Wrong answers. Please try again.');
    // Stay on the same page
  }
};
</script>

<style scoped>
.background {
  background-color: #3498db;
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}

.quiz-container {
  max-width: 90%;
}

.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 9999;
}

.custom-modal {
  background-color: #fff;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.3);
  padding: 20px;
}

.full-width {
  width: 100%;
}

.modal-body input {
  border: none;
  border-radius: 0;
  border-bottom: 1px solid #ccc;
  padding: 10px 0;
  box-sizing: border-box;
}

.modal-footer {
  text-align: center;
}

.center-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.transparent-bg {
  background-color: transparent;
  border: none;
}

.full-width-button {
  width: 100%;
}

.welcome-text {
  margin-bottom: 20px;
}

.welcome-text h2 {
  font-size: 28px;
}

.welcome-text h4 {
  font-size: 18px;
}

.quiz {
  list-style-type: none;
  padding: 0;
}

.quiz li {
  margin-bottom: 20px;
}

.quiz li p {
  margin-bottom: 10px;
}

.quiz li .options {
  display: flex;
  justify-content: space-around;
}

.quiz li label {
  display: inline-block;
  margin-bottom: 10px;
}

.right-answer {
  margin-top: 20px;
}

@media (max-width: 768px) {
  .welcome-text h2 {
    font-size: 24px;
  }

  .welcome-text h4 {
    font-size: 16px;
  }
}
</style>
