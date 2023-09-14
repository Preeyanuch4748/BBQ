<template lang="">
<div>
    <ul>
     <li><a class="active" href="#home">หน้าหลัก</a></li>
     <li><a href="#news">ข่าวสาร</a></li>
     <li><a href="#contact">ติดต่อเรา</a></li>
     <li><a href="#about">เกี่ยวกับเรา</a></li>
    </ul>
    <ul>
        <li><b class="active" href="#LogIn">เข้าสู่ระบบ</b></li>
    </ul> 
    </div>
</template>
<script>
export default {
    
}
</script>
<style scoped>
ul {
  list-style-type: none;
  margin: 0;
  padding: 1;
  overflow: hidden;
  background-color: #d12323;
}

li {
  text-align: center;
  margin: 0 5px;
}

li.right {
  float: right; /* ย้ายไปด้านขวา */
}

li a, li b {
  display: block;
  color: rgb(244, 234, 234);
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

li a:hover {
  background-color: #fedbdb;
  color: rgb(96, 65, 65);
  border: 0px solid #ee6868;
}

li b:hover {
  background-color: #fbabab;
  color: rgb(93, 61, 61);
  border: 1px solid #ede5e5;
  
}
</style>