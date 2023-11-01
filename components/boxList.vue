<template>
<div class="boxList">
    <div  v-for="box in boxes" :key="box.title" class="boxListVfor">

            <details v-bind:class="[box.boxNumber]">
                <summary class="boxTitle">{{box.title}}</summary>
                <p class="boxText">{{box.primary}}</p>
            </details>
        </div>
    </div>
</template>

<script>
    export default{
        auth:false,
        
            data(){
            return{
            isActive:true,
            boxes:[
                {boxNumber:"box1",title:"プロフィール",primary:"わたしについて。display:blockの要素に対しては、margin-leftとmargin-rightのそれぞれの値をautoにすることで水平方向に中央寄せできます。",isActive:false},
                {boxNumber:"box2",title:"twitter",primary:"twitterです。",isActive:false},
                {boxNumber:"box3",title:"絵",primary:"これは絵です",isActive:false},
                {boxNumber:"box4",title:"スケジュール",primary:"これからのスケジュールｼﾞｭﾙ",isActive:false},
                ]
            }
        },
    
    //methods:{
    //toggle(){
      //  this.isActive=!this.isActive
   // }
    //}


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



.box1,.box2,.box3,.box4{
    position:relative;
    border:solid #00DC82 1px;
    height:auto;
    margin: 4px;
    transition: transform 0.4s;
}

 .box1{
}


.box2{
    grid-row:2/3;
}

.box3{
    grid-row:3/4;
}
.box4{


}


.boxTitle{
margin-top: auto;
padding:10px;
}

summary{position:relative;display: block;padding-left: 12px;}
summary::-webkit-details-marker{desplay:none;}

summary:before,summary:after{
    content:"";
    margin:auto;
    position:absolute;
    top:0;
    bottom:0;
    left:0;
}
summary::before{
    width:12px;
    height:12px;
    background-color: rgb(44, 157, 255);
}

summary::after{
    width:12px;
    height:12px;
    background-color: aliceblue;
}



.boxText{}
</style>