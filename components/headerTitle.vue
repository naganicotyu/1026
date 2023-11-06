<template>
  <div class="headerBody">
    <p class="headerTitle">KON:/> Website/home --information</p>
    <p class="headerInstraction">KONのHomepageにようこそ。今後の活動情報などを掲載しています。</p>

  </div>
</template>

<style>
@font-face{
        font-family:'16font';
        src:url('@/static/fonts/KH-Dot-Kodenmachou-12-Ko.ttf') format("truetype");
    }

    *{
      font-family:'16font';
    }

    .headerBody{
      margin-top:0px;
      padding: 20px;

    }


.headerTitle{


    color: #e2e2e2;
    font-size: 28px;
    border-right: 6px solid black;
    overflow: hidden;
    white-space: nowrap;
    margin-top: 0px;
    margin-bottom: 14px;
    margin-left: auto;
    margin-right: auto;
    width:0;
    animation: typing 2s steps(30, end) forwards, cursol 0.5s step-end infinite;
}

.headerInstraction{
  text-align: center;
  color: aliceblue;
  margin-bottom: 48px;


}



@keyframes typing{
  0% { width: 0%; }
  100% { width: 17em; }
}

@keyframes cursol{
  0%{ border-color: transparent; }/*消滅*/
  50%{ border-color: rgb(3, 255, 137); } /*出現*/
  100%{ border-color: transparent; }/*消滅*/
}
</style>