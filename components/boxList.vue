<template>
<div class="boxList">
    <div  v-for="box in boxes" :key="box.title" class="boxListVfor">
        <div bind:class='[box.boxNumber,{active:isActive}]'>

            <p class="boxTitle">
                {{box.title}}
            </p>

            <p class="boxText">
                {{box.primary}}
            </p>

        </div>

        </div>
    </div>
</template>

<script>
    export default{auth:false,data(){return{boxes:[
                {boxNumber:"box1",title:"プロフィール",primary:"わたしについて。"},
                {boxNumber:"box2",title:"twitter",primary:"twitterです。"},
                {boxNumber:"box3",title:"絵",primary:"これは絵です"},
                {boxNumber:"box4",title:"スケジュール",primary:"これからのスケジュールｼﾞｭﾙ"},
    ]}}}

</script>

<style>
.boxList{
    margin:10ox;
    width: 800px;
    height:1200px;
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 1fr 2fr 1fr;
}

.boxListVfor{}

.box1{
    grid-row:2/3;
    grid-column:1/2;
}


.box2{
    grid-row:2/3;
    grid-column:2/3;
}

.box3{
    grid-row:4/3;
    grid-column:1/2;
}

.box4{
    grid-row:3/4;
    grid-column:2/3;
}

.box1 active{
    grid-row:2/3;
    grid-column:1/3;
}


.box2 active{
    grid-row:2/3;
    grid-column:1/3;
}

.box3 active{
    grid-row:4/3;
    grid-column:1/3;
}

.box4 active{
    grid-row:3/4;
    grid-column:1/3;
}

.box1 up{
    grid-row:1/2;
    grid-column:1/2;
}


.box2 up{
    grid-row:1/2;
    grid-column:2/3;
}

.box3 up{
    grid-row:4/5;
    grid-column:1/2;
}

.box4 up{
    grid-row:4/5;
    grid-column:2/3;
}
.boxTitle{}

.boxText{}
</style>