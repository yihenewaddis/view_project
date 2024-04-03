<template>
    <form @submit.prevent="handleSubmit">
        <label>Email</label>
        <input type="email" v-model="email">
        <label>password</label>
        <input type="password" v-model="password">
        <select v-model="options">
            <option value="web developer">web developer</option>
            <option value="app app developer">app developer</option>
        </select>
        <div>
            <input type="checkbox" v-model="termAndCondition">
            <label> accept terms and conditions</label>
        </div>
        <div>
            <input type="checkbox" value="yihenew" v-model="name">
            <label> website developer </label>
        </div>
        <div>
            <input type="checkbox" value="addis" v-model="name">
            <label> mobile app developer</label>
        </div>
        <div>
            <input type="checkbox" value="kassa" v-model="name">
            <label> blog app developer</label>
        </div>
        <div>
            <input type="text" value="kassa" v-model="singleskil" @keypress="handleSkils">
            <label> blog app</label>
        </div>
        <button>submit</button>
    </form>
</template>

<script>
export default {
    data(){
        return{
            email:'mario',
            password:'',
            options:'web developer',
            termAndCondition:false,
            name:[],
            singleskil:'',
            skill:[]
        }
    },
    methods:{
        handleSkils(e){
        if(e.key ===',' && this.singleskil ){
            this.skill.push(this.singleskil)
            this.singleskil=''
            console.log(this.skill)
        }
        },
        handleSubmit(){
            
        }
    }
}
</script>

<style>
form{
    max-width: 100%;
    margin: 20px auto;
    background-color: white;
    text-align: left;
    padding: 10px;
    border-radius: 10px;
}
label{
    letter-spacing: 1px;
    color: gray;
    font-weight: bold;
    display: inline-block;
    margin: 10px;
}
input ,select{
    max-width: 100%;
    display: block;
    box-sizing: border-box;
    border: none;
    border-bottom: 1px solid gray;
    color:rgb(135, 138, 140); 
    padding: 10px 8px;
    margin-top: 5px;
}
input[type = 'checkbox']{
    display: inline-block;
    padding-top: 2px;
}
</style>