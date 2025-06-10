<template>
<v-container fluid>
    <v-row>
        <v-col cols="12" md="4">
<pre>
<h1>Vue Methods</h1>
-vue 매서드는 '메서드' 속성 아래 vue인스턴스에 속하는 함수
-vue 매서드는 이벤트 처리와 함께 사용하면 더 복잡한 작업을 수행하는데 유용하다
-이벤트처리 외에도 다른 작업을 수행하는데 사용할수 있다
</pre>
<br/>
<br/>
<br/>
            <p>Click on the box below</p>
            <div class="app">
                <div v-on:click="changeText">
                    {{ text }}
                </div>
            </div>
        </v-col>
            
        <v-col cols="12" md="4">
            <h1>이벤트 객체를 사용하여 호출</h1>
            <div class="mouse">
                <div v-on:mousemove="mousePos">
                    <span>
                        xPos:{{ xPos }}
                    </span><br/>
                    <span>
                        yPos:{{ yPos }}
                    </span><br/>
                </div>
            </div>
        </v-col>

        <v-col cols="12" md="4">
            <h1>Vue write</h1>
            <div class="rot">
                <textarea v-on:input="writeText" rows="8" cols="30" placeholder="Start writing..."></textarea>
                <div>
                    <span>{{ txt }}</span>
                </div>
            </div>
        </v-col>
    </v-row>
</v-container>
</template>

<script>
//const app=Vue.createApp  이것은 cdn 걸었을때 사용하는것
export default{
    data(){
        return{
            text:'',
            xPos:0,
            yPos:0,
            txt:'',
        }
        
    },
    methods:{
        changeText(){
            this.text='Hello world'
        },
        mousePos(event){
            this.xPos=event.offsetX
            this.yPos=event.offsetY
        },
        writeText(event){
            this.txt=event.target.value
        }
    },
}
</script>


<style>
.app{
    border:1px dashed black;
    width: 200px;
    padding: 0 20px 20px 20px;
}
.app>div{
    width:140px;
    height:60px;
    background-color: lightgreen;
    padding:20px;
}

.mouse{
    border:1px inset;
    width:100%;
    padding:0 20px 20px 20px;
}
.mouse div{
    width:90%;
    height: 80px;
    background-color: lightcoral;
    padding: 20px;
}
.mouse div span{
    font-weight:bold;
}

.rot{
    border:1px dashed black;
    width:300px;
    padding:20px;
}
.rot>div{
    width:100%;
    position: relative;
    margin-top:10px;
    aspect-ratio:1;
    background-image: url(../../assets/img/img_notebook.png);
    background-size: 100%;
    overflow: hidden;
}
.rot>textarea{
    width: 100%;
    box-sizing: border-box;
}
.rot>div>span{
    width:80%;
    font-weight: bold;
    line-height: 1.2em;
    transform-origin:0 0 ;
    rotate:33deg;
    position: absolute;
    top:45px;
    left:70px;
    font-family:'Courier New',Courier,monospace ;
}
</style>

