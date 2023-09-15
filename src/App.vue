<script setup>
  import{ ref } from "vue";


  const travel = ref("");
  const money = ref(0);

  const Details = ref({
    name: "",
    tel: "",
    date: "",
    time: "",
    tables: ""
  });
  
  const travelList = ref([
    {name:'TEA FAC', price:80, size: {s:80, m: 150, l: 200}, img:"https://img.wongnai.com/p/400x0/2022/10/21/426628784fe84b8eb8dbbd84df1d3c43.jpg" },
    {name:'Ristr8to', price: 50 , size: {s:50, m: 100, l: 150}, img:"https://www.wakeup24hrs.com/pic-2020/Ristr8to.jpg" },
    {name:'ROAST8RY LAB', price: 90 , size: {s:90, m: 120, l: 150}, img:"https://ak-d.tripcdn.com/images/1mi6c2234anw1nusgCE26_W_400_0_R5_Q90.jpg" },
    {name:'Bart Coffee', price: 100 , size: {s:100, m: 150, l: 200}, img:"https://img.wongnai.com/p/400x0/2018/05/30/23ecf8e3cf4141e28fedb93be704356d.jpg" },
    {name:'di BOSCO COFFEE SPECIALIST', price: 30 , size: {s:30, m: 50, l: 100}, img:"https://asian-traveller.com/en/wp-content/uploads/2021/01/bosco31_wm-scaled.jpg" }, 
    {name:'Looper & Co.', img:"https://img.salehere.co.th/p/1200x0/2023/05/25/62bokp7oqtrn.jpg"}
  ]);
  
  const bookingList = ref([
  ]);

  function booking(restaurant, details) {

  const bookingData = {
    restaurantName: restaurant.name,
    name: details.name,
    tel: details.tel,
    date: details.date,
    time: details.time,
    tables: details.tables,
  };
  
  bookingList.value.push(bookingData);

  Details.name = '';
  Details.tel = '';
  Details.date = '';
  Details.time = '';
  Details.tables = '';
  alert("การจองสำเร็จ!!! โปรดเช็คการจองที่ด้านล่างของเว็บ")
}


</script>

<template>
  <h1 style="color: rgb(255, 114, 114) ;">🍵เลือกร้านกาแฟที่ต้องการ🍵</h1> <br>
  <div class="container-input" style="background-color: #ffe1c6;">
    <h4 style="color: rgb(214, 28, 28); font-weight: bold;">** กรุณากรอกข้อมูลให้ครบถ้วนก่อนจองโต๊ะ **</h4>
    <div class="cont">
          <div class="text-input">
            ชื่อผู้จอง&nbsp; <input type="text" v-model="Details.name" required> 
          </div>
          <div class="text-input">
          โทรศัพท์&nbsp; <input type="tel" v-model="Details.tel" required> 
          </div>
          <div class="text-input">
            จำนวน&nbsp; <input type="number" v-model="Details.tables" required> 
          </div>
          <div class="text-input">  
            วัน&nbsp; <input type="date" v-model="Details.date" required>
          </div>
          <div class="text-input">
            เวลา&nbsp; <input type="time" v-model="Details.time" required>
          </div>
    </div>
  </div>
  <div class="container text-center" style="background-color: ; border-radius: 10px;">
    <div class="row" align="center">
      <div class="col" v-for="(item, index) in travelList" :key="index">
        <div class="card" style="width: 18rem; background-color: #e1bcea; margin: 30px; border-radius: 10px;">
          <img :src="item.img" class="card-img-top" alt="...">
          <div class="card-body">
            <h5 class="card-title">{{ item.name }}</h5>
            <p class="card-text">ร้านกาแฟเชียงใหม่ในดวงใจ ที่ไปกินตั้งแต่ยังมีแค่สาขาเดียว เป็นร้านกาแฟที่โดดเด่นด้วยความคิดสร้างสรรค์ในการผสมผสานเมนูแปลก ๆ เข้ากับกาแฟ และมีจุดเด่นคือ Cold Brew ที่รสละมุน ไม่เปรี้ยว ไม่ขม กลมกล่อมและเด็ดมาก</p>
             <br>
            <a href="#" class="btn" @click="booking(item, Details)">จองโต๊ะ</a>
          </div>
        </div>
      </div>
    </div>
  </div> <br>
  <table class="table table-dark table-striped" v-if="bookingList.length > 0">
  <thead>
    <h4>รายละเอียด</h4>
    <tr>
      <th scope="col">ชื่อร้าน</th>
      <th scope="col">ชื่อผู้จอง</th>
      <th scope="col">เบอร์โทร</th>
      <th scope="col">ว/ด/ป</th>
      <th scope="col">เวลา</th>
      <th scope="col">จำนวนโต๊ะ</th>
    </tr>
  </thead>
  <tbody>
    <tr v-for="(booking, index) in bookingList" :key="index">
      <td>{{ booking.restaurantName }}</td>
      <td>{{ booking.name }}</td>
      <td>{{ booking.tel }}</td>
      <td>{{ booking.date }}</td>
      <td>{{ booking.time }}</td>
      <td>{{ booking.tables }}</td>
    </tr>
  </tbody>
</table> <br>

  <div class="color">
    <h1>ไปเที่ยวกันมั้ย👩🏻‍💻?</h1>
    <input type="radio" value="a" v-model="travel" />ภูเขา
    <input type="radio" value="b" v-model="travel" />ทะเล &nbsp;
    จำนวนเงิน &nbsp;
    <input type="number" v-model="money">
    <div v-if="money < 100">อยู่บ้านนอน💤</div>
    <div v-else-if="money >= 100 && money < 1000000">ขึ้นรถไปเที่ยว🚗</div>
    <div v-else-if="money >= 1000000">ขับเครื่องบินส่วนตัว🛩️</div>
    <div v-else-if="money <= 0">กรุณากรอกจำนวนเงิน</div>
    <div v-if="travel === 'a' ">⛰️</div>
    <div v-else>🏝️</div>
    <br>
    <button type="button" v-if="money < 50" disabled style="background-color: rgba(255, 0, 0, 0.142);">Let's Go</button>
    <button type="button" v-else style="background-color: rgb(252, 77, 13);">Let's Go</button>
  </div><br>
    <footer class="footer">
    <div class="container">
      <div class="footer-copyright">
      &copy; 2023 บริการทุกระดับประทับใจ ขอบคุณที่ใช้บริการ
    </div>
  </div>
  </footer>
</template>
