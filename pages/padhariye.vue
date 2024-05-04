<template>
  <div class="background">
    <div class="content">
      <h1><u>Hey Improwised Family!!</u></h1>
      <br>
      <p class="intro">Get ready to break out the party hats and join us in celebrating a monumental moment in our company's journey! Guess what? We're about to hit a major milestone that's making us feel like we're on cloud nine! That's right, we're not just turning 13 - we're hitting the glorious tween years of our corporate existence. And just like any tween, we're ready to celebrate in style!</p>

      <p class="details">So, mark your calendars and save the date for a special lunchtime celebration on this 18th of May! It's going to be a blast from the past with a dash of future-forward flair. Think nostalgic tunes, throwback treats, and maybe even a few surprises that will transport us back to our younger years (but with a lot more wisdom and experience under our belts!).</p>

      <p class="details">We couldn't have reached this amazing milestone without each and every one of you, so let's take this opportunity to toast to our past achievements, embrace the present, and set our sights on an even brighter future ahead.</p>

      <p class="details">Come hungry, come festive, and come ready to party like it's 13 years ago (but better)! Prepare yourselves for an afternoon packed with tasty treats, laughter, and maybe a few surprises along the way. We'll have delicious food, refreshing beverages, and of course, the company of your fantastic colleagues to make this celebration truly unforgettable.</p>
      
      <p class="footer">See you there!<br>Warm Regards!</p>

      <div class="cta">
        <a href="https://docs.google.com/forms/d/e/1FAIpQLSfTvu0-ACJsjxROpzrowUqLPcekR5xVoiiyNPJQD29YPEJszw/viewform" class="button">NEXT -></a>
      </div>
    </div>
  </div>
</template>

<style scoped>
.background {
  background-color: #3498db;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  font-family: 'Arial', sans-serif;
}

.content {
  max-width: 90%;
  padding: 20px;
  background-color: rgba(255, 255, 255, 0.9);
  border-radius: 10px;
  box-shadow: 0px 0px 20px rgba(0, 0, 0, 0.2);
}

h1 {
  font-size: 28px;
  margin-bottom: 10px;
  text-align: center;
}

.intro, .details, .footer {
  font-size: 16px;
  margin-bottom: 15px;
  text-align: left;
}

.cta {
  text-align: center;
}

.button {
  display: inline-block;
  padding: 10px 20px;
  background-color: #3498db;
  color: #fff;
  text-decoration: none;
  border-radius: 5px;
  transition: background-color 0.3s ease;
}

.button:hover {
  background-color: #2980b9;
}

@media screen and (max-width: 768px) {
  .content {
    padding: 10px;
  }

  h1 {
    font-size: 24px;
  }

  .intro, .details, .footer {
    font-size: 14px;
  }
}
</style>
