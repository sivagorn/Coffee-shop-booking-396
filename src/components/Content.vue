<template>
<div class="container text-center">
    <div class="row">
        <div class="col mb-4" v-for="(i, index) in travelList" :key="index">
            <div class="card" style="width: 20rem;">
                <img :src="i.img" class="card-img-top" alt="..." />
                <div class="card-body">
                    <h5 class="card-title">{{ i.name }}</h5>
                    <ul class="card-text">
                        <li>บริการ : ทุกวัน 9.00 – 18.30 น.</li>
                        <li>จำนวน 4 คนต่อ 1 โต๊ะ</li>
                        <li>ราคาโต๊ะ = 50 บาท ( 4 ชั่วโมง )</li>
                        </ul>            
      <button @click="reserveTable(index)" class="main-button">จองโต๊ะ</button>
            <p>จำนวนการจอง: <span>{{ bookingCount[index] }}</span></p>
                </div>
            </div>
        </div>
    </div>
</div>


</template>

<script setup>
import { ref } from "vue";

const travel = ref("");
const money = ref(0);

//const travelList=ref(['The Caferista','The Simple','ฮักมาว แม่โจ้','Have-A-Hug','Café Woodhouse','Imagines House'])
const travelList=ref([
    { name: "The Caferista", price: 40, size: { s: 80, m: 150, l: 200 }, img:"https://cdn.chiangmainews.co.th/wp-content/uploads/2018/01/07083746/1-8-800x566.jpg" },
    { name: "The Simple", price: 40, size: { s: 80, m: 150, l: 200 }, img:"https://cdn.chiangmainews.co.th/wp-content/uploads/2018/01/07083745/2-8-800x566.jpg" },
    { name: "ฮักมาว แม่โจ้", price: 40, size: { s: 80, m: 150, l: 200 }, img:"https://cdn.chiangmainews.co.th/wp-content/uploads/2018/01/07083745/3-11-800x566.jpg" },
    { name: "Have-A-Hug", price: 40, size: { s: 80, m: 150, l: 200 }, img:"https://cdn.chiangmainews.co.th/wp-content/uploads/2018/01/07083744/4-10-800x566.jpg" },
    { name: "Café Woodhouse", price: 40, size: { s: 80, m: 150, l: 200 }, img:"https://cdn.chiangmainews.co.th/wp-content/uploads/2018/01/07083744/5-10-800x566.jpg" },
    { name: "Imagines House", price: 40, size: { s: 80, m: 150, l: 200 }, img:"https://cdn.chiangmainews.co.th/wp-content/uploads/2018/01/07083743/6-8-800x566.jpg" },
]);

const bookingList = ref([
    "The Caferista","The Simple","ฮักมาว แม่โจ้","Have-A-Hug","Café Woodhouse","Imagines House"
]);


function booking(name){
    bookingList.value.push(name)
}

const bookingCount = ref(new Array(travelList.value.length).fill(0));

function reserveTable(index) {
  bookingCount.value[index] += 1;
}

</script>

<style>

</style>