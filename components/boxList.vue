<template>
<div class="boxList">
    <div  v-for="box in boxes" :key="box.title" class="boxListVfor">

            <div v-bind:class="box.boxNumber">
                <div @click="onClickTitle()" class="boxTitle">{{box.title}}</div>
                <transition name="boxTextSwitch">
                <div v-show="active" class="boxText"><p>{{box.primary}}</p></div>
            </transition>
            </div>
            </div>
    </div>
</template>

<script>
    export default{
        
            data(){
            return{
                active:false,
                boxes:[
                {boxNumber:"box1",title:"プロフィール",primary:"わたしについて。display:blockの要素に対しては、margin-leftとmargin-rightのそれぞれの値をautoにすることで水平方向に中央寄せできます。",isActive:false},
                {boxNumber:"box2",title:"twitter",primary:"twitterです。",isActive:false},
                {boxNumber:"box3",title:"絵",primary:"これは絵です",isActive:false},
                {boxNumber:"box4",title:"スケジュール",primary:"これからのスケジュールｼﾞｭﾙ",isActive:false},
                ]
            }
        },
    
    methods:{
    onClickTitle(){
            this.active=!this.active;
        }
    }

}


</script>

<style>
.boxList{
    margin:10px;
    width: 600px;
    height:600px;
    margin-top: 0px;
    margin-left: auto;
    margin-right: auto;
    transition: transform 0.4s;

}
.boxTitle{
    margin-top: auto;
    margin-right: 0px;
    padding:10px;
    border:solid #00DC82 1px;
}

.boxPerents{
    position:relative;display: block;
    padding-left: 0px;}

.boxText{
    height:200px;
    padding:10px;
    overflow: hidden;
}

.boxTextSwitch-leave-active,.boxTextSwitch-enter-active{
    transition:height 0.5s linear;
}
.boxTextSwitch-enter,.boxTextSwitch-leave-to{
    height:0;
}



.box1,.box2,.box3,.box4{
    position:relative;
    border:solid #ef11f7 3px;
    height:auto;
    margin: 4px;
    transition: transform 0.4s;
}

 .box1{
    }

.box3{
    
}
.box4{


}



</style>