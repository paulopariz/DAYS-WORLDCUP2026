<template>
    <div class="time">
        <div class="group">
            <p>{{days}}</p>
            <span>days</span>
        </div>
        <div class="group">
            <p>{{hours % 24}}</p>
            <span>hours</span>
        </div>
        <div class="group">
            <p>{{mins % 60}}</p>
            <span>min</span>
        </div>
        <div class="group">
            <p>{{sec % 60}}</p>
            <span>sec</span>
        </div>
    </div>
</template>

<script>

import { ref } from "@vue/reactivity";
export default {
    setup(){
        const days = ref(0);
        const hours = ref(0);
        const mins = ref(0);
        const sec = ref(0);
        const launchDate = new Date('8 June 2026');

        setInterval(() => {
            const currDate = new Date();
            const launchTime = launchDate - currDate;

            sec.value = parseInt(launchTime / 1000);
            mins.value = parseInt(sec.value / 60);
            hours.value = parseInt(mins.value / 60);
            days.value = parseInt(hours.value / 24)
        }, 1000);

        return {days, hours, mins, sec}
    }
}
</script>

<style>
.time{
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 58px;
    font-family: 'Roboto Mono', monospace;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}

.group{
    display: grid;
    text-align: center;
    padding: 10px;
    background-color: rgba(255, 255, 255, 0.4);
    -webkit-backdrop-filter: blur(5px);
    backdrop-filter: blur(5px);
    width: 185px;
    border: 1px solid #ffffff;
    border-radius: 10px;
    box-shadow: 1px 1px 16px #ffffff63;
}

p{
    font-size: 60px;
    font-weight: 700;
}
span{
    font-size: 16px;
    color: black;
    font-weight: 800;
    letter-spacing: 1px;
}

@media(max-width: 991px){
    .time{
      gap: 30px;
    }
    .group{
        width: 160px;
    }
    p{
        font-size: 55px;
    }
  }

  @media(max-width: 768px){
    .time{
        display: grid;
        grid-template-columns: 1fr 1fr;
    }
  }
  @media(max-width: 440px){
    .time{
        gap: 15px;
    }
    .group{
        width: 130px;
    }
    p{
        font-size: 2.6875rem;
    }
    span{
        font-size: 15px;
        letter-spacing: 0px;
    }
  }

</style>