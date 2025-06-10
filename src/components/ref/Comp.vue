<template>
    <v-container>
        <v-row>
            <v-col cols="12" md="4">
                
<pre>
<h1>Computed Properties</h1>
-다른 속성에 따라 달라지는 점을 제외하면 데이터 속성과 유사하다
-메서드처럼 작성되지만 입력 인수를 허용하지 않는다
-종속성이 병경되면 자동으로 업데이트 되고 메서드는 이벤트 처리와 같이 무언가가 발생하면 호출
-다른것에 의존하는 것을 출력할때 사용됨
-동적이다: 하나 이상의 데이터의 속성값에 따라 변경된다
-computed라는 예약된 이름을 갖는다
-toggle과 비슷,양면성을 가지고 있음
</pre>
<br/>
<br/>
<br/>

<form>
    <p>
        체크박스를 체크해 보아요 
        <label class="form-label">
            <input type="checkbox" class="form-check" v-model="chbxVal">
            {{ isImportant }}
        </label>
    </p>
</form>
            </v-col>
            <v-col cols="12" md="4">
                <h2>{{ name }}</h2>
                <p>{{ message }}</p>
            </v-col>
            <v-col cols="12" md="4">
                <h1>Vue 템플릿</h1>
                <p>이것은 파라미터</p>
            </v-col>
        </v-row>
    </v-container>
</template>


<script>
export default{
    template:
    `<h1>{{ msg }}</h1> 
    <p>이것은 파라미터</p>`,
    data(){
        return{
            chbxVal:false,
            name:'Apples',
            message:'i like...',
            msg:'세계여 안녕',
        }
    },
    computed:{
        isImportant(){
            if(this.chbxVal){
                return 'yes'
            }else{
                return 'no'
            }
        }
    }
}
</script>


<style>
form{
    border:dashed black 1px;
    display: inline-block;
    padding: 10px;
}
label{
    padding: 5px;
}
label:hover{
    cursor:pointer;
    background-color: lightgrey;
    border-radius: 5px;
}
</style>


