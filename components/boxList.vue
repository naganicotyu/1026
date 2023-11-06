<template>
    <div class="boxList">
        <div  v-for="box in boxes" :key="box.title">
                <div v-bind:class="box.boxNumber" @click="onClickTitle(box)">
                    <div class="boxTitle"><div v-show="box.isActive" class="iconFlash">■</div><div>{{box.title}}</div></div>
                    <transition name="boxTextSwitch">
                    <div v-show="box.isActive" class="boxText"><p>{{box.primary}}</p><p>{{box.secondary}}</p><a v-bind:href="box.link">{{ box.link }}</a></div>
                </transition>
                </div>
                </div>
        </div>
    </template>
    
    <script>
        export default{
            
                data(){
                return{
                    boxes:[
                    {boxNumber:"box1",title:"プロフィール",primary:"(名前:HN/生年月日:1998-06-29/趣味:酒)",secondary:"和歌山大学システム工学部卒。WEBシェーダーに関する技術に熱中する。卒業後フリーターとなり、塾講師やデータ校正のバイトをしながらその日暮らしを謳歌する。趣味は言語学とカメラと電子楽器収集(特にKORG製品)。",isActive:false},
                    {boxNumber:"box2",title:"twitter",primary:"twitterです。基本的に作品の公開はこちらで行っております。",link:"https://twitter.com/K0NEHI",isActive:false},
                    {boxNumber:"box3",title:"絵",primary:"//カルーセルメニューの準備中。少々お待ちください。",secondary:"",isActive:false},
                    {boxNumber:"box4",title:"スケジュール",primary:"ふわふわ予定：現在、VR空間における全天球webサイトにを鋭意制作中。ユビキタスの変遷により、webサイトも平面からレイヤーへ、レイヤーからVRへと進化していくのでは？という問いから出発しました。",secondary:"マジ予定：12/2 歯医者　予約",isActive:false},

                    ]
                }
            },
        
        methods:{
            onClickTitle(selectedBox) {this.boxes.forEach((box) => {
                                if (box !== selectedBox) {
                                box.isActive = false;
                                }
                            });
            
            selectedBox.isActive = !selectedBox.isActive;
            }
            }


    }
    
    
    
    
    </script>
    
    <style>
    @font-face{
        font-family:'16font';
        src:url('@/static/fonts/KH-Dot-Kodenmachou-12-Ko.ttf') format("truetype");
    }

    .boxList{
        border:2px double #ffffff;

        margin:10px;
        width: 650px;
        height:120%;
        margin-top: 0px;
        margin-left: auto;
        margin-right: auto;
        transition: transform 0.4s;
    
    }
    .boxTitle{
        display: flex;
        margin-top: auto;
        margin-right: 0px;
        padding:10px;
    }
    
    .iconFlash{
        animation:wink 0.2s linear infinte;
        color: rgb(0, 255, 13);

    }
    @keyframes wink{
  0%{ opacity: 1;}/*消滅*/
  50%{ opacity: 0; } /*出現*/
  100%{ opacity: 1; }/*消滅*/
}

    
    .boxPerents{
        position:relative;display: block;
        padding-left: 0px;}
    
    .boxText{
        height:100px;
        padding:0px;
        overflow: hidden;
    }
    
    .boxTextSwitch-leave-active,.boxTextSwitch-enter-active{
        transition:height 0.5s linear;
    }
    .boxTextSwitch-enter,.boxTextSwitch-leave-to{
        height:0;
    }
    
    
    
    .box1,.box2,.box3,.box4{

        color: #e2e2e2;
        margin: 8px;
        transition: transform 0.4s;
        font-family:'16Font';
    }
    
    .box1{
        border:inset #ffffff 3px;
        }
    .box2{
        border:inset #ffffff 3px;
    }
    
    .box3{
        border:inset #ffffff 3px;
        
    }
    .box4{
        border:inset #ffffff 3px;
    
    
    }
    
    
    
    </style>