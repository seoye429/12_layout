<template>
    <v-container fluid>
        <v-row>
            <v-col cols="12" md="4">
                <h1>지시어</h1>
                <div class="pre">
                <pre>
                -v-bind: 태그의 속성을 vue인스턴스 내부의 데이터 변수에 연결
                -v-if: 조건부 렌더링 <code>v-if,v-else-if,xv-else</code>
                -v-show:true가 되면 보이고,false가 되면 안보이는거임
                -v-for:정해진 크리 만큼 반복
                -Event:
                -v-on:
                </pre>
                </div>
                <div class="" id="msg">
                    {{ message }}
                </div>
            </v-col>

            <v-col cols="12" md="4">
                <h1>v-bind</h1>
                <p>line</p>
                <section v-bind:class="vueClass">이 요소는 핑크bg이다</section>
                <p v-bind:style="{fontSize:size}">글자를 키워 볼까나???</p>
                <div v-bind:style="{backgroundColor:isImportent ? 'lightcoral':'lightgrey'}">조건부 배경색 칠하기</div>
            </v-col>

            <v-col cols="12" md="4">
                <div class="" v-if="text.includes('pizza')">
                    <p>텍스트에 피자 단어가 포함 되어 있음</p>
                    <img src="../../assets/img/img_pizza.svg" class="mrPizzas">
                </div>

                 <div class="" v-else-if="text.includes('burrito')">
                    <p>텍스트에 부리또 단어가 포함 되어 있음</p>
                </div>

                <div class="" v-else>
                    <p>텍스트에 피자/부리또 단어가 포함 되어 있지 않음</p>
                </div>
            </v-col>
        </v-row>

        <v-row>
            <v-col cols="12" md="8">
                <ol>
                    <li v-for="x in manyFoods">{{ x }}</li>
                </ol>
            </v-col>

            <v-col cols="12" md="4">
                <div class="border w-100 wrap">
                <figure v-for="x in manyFood">
                    <img v-bind:src="x.url" class="mrPizza">
                    <figcaption>{{ x.name }}</figcaption>
                </figure>
                </div>
            </v-col>
        </v-row>

        <v-row>
            <v-col cols="12">
                <h1>Basic css Transition</h1>
                <v-btn @click="this.doesRotate=true">Rotate</v-btn>
                <div :class="{rotate:doesRotate}" id="rect"></div>
            </v-col>
        </v-row>


    </v-container>
</template>

<style>
#msg{
    padding: 10px;
    font-size:x-large;
    background-color: lightgreen;
}
.pinkBG{
    background-color: lightpink;
}
.mrPizza{
    width:100%;
}
figure{
    width: 100px;
    padding:10px;
    margin: 10px;
    background: lightskyblue;
    border-radius:5px;
}
figcaption{
    text-align:center;
}
.mrPizzas{
    width: 30%;
}
.wrap{
    display: flex;
    flex-wrap:warp;
}
.rotate{
    rotate:1800deg;
    transition:all 3s ease-in-out;
}
#rect{
    border:2px solid;
    background: lightcoral;
    width:60px;
    height: 60px;
    margin-top: 10px;
}
/* .pre{
    width: 30%;
} */
</style>

<script>
//html로 뷰를 학습할때는 const app=Vue.createApp 으로 사용했지만 현재는 아니다
export default{
    data(){
        return{
            message:"Hello world",
            vueClass:"pinkBG",
            size:'48px',
            isImportent:true,
            text:'I like burrito,pizza,...',
            manyFoods:['Burrito','Salad','Cake','Soup','Fish','Pizza','Rice'],
            manyFood: [
                {name: 'Burrito', url: 'src/assets/img/img_burrito.svg'},
                {name: 'Salad', url: 'src/assets/img/img_salad.svg'},
                {name: 'Cake', url: 'src/assets/img/img_cake.svg'},
                {name: 'Soup', url: 'src/assets/img/img_soup.svg'},
                {name: 'Fish', url: 'src/assets/img/img_fish.svg'},
                {name: 'Pizza', url: 'src/assets/img/img_pizza.svg'},
                {name: 'Rice', url: 'src/assets/img/img_rice.svg'}
            ],
            doesRotate:false,
        };
    }
}
</script>

