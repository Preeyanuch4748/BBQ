<template>
    <footer class="footer">
      <div class="container">
        <div class="footer-content">
          <div class="footer-logo">
            <img src="https://i.pinimg.com/564x/53/9f/1d/539f1d4615e269e01d9d4ebc057b2dd1.jpg" alt=" Logo" />
            <h2> กิน กับ Pk</h2><br>
          </div>
          <div class="footer-links">
            <ul>
              <li><router-link to="/">หน้าหลัก</router-link></li>
              <li><router-link to="/about">เกี่ยวกับเรา</router-link></li>
              <li><router-link to="/contact">ติดต่อเรา</router-link></li>
            </ul>
          </div>
          <div class="footer-social">
            <a href="#"><i class="fab fa-facebook"></i></a>
            <a href="#"><i class="fab fa-twitter"></i></a>
            <a href="#"><i class="fab fa-linkedin"></i></a>
          </div>
        </div>
        <div class="footer-copyright">
          &copy; {{ currentYear }} My Company. All Rights Reserved.
        </div>
      </div>
    </footer>
  </template>
  
  <script>
  export default {
    data() {
      return {
        currentYear: new Date().getFullYear()
      };
    }
  };
  </script>
  
  <style scoped>
  /* CSS styles for your footer component */
  .footer {
    background-color: #4f4f4f;
    color: white;
    padding: 20px 0;
  }
  
  .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  
  .footer-content {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: center;
  }
  
  .footer-logo {
    display: flex;
    align-items: center;
  }
  
  .footer-logo img {
    width: 40px;
    height: 40px;
    margin-right: 10px;
  }
  
  .footer-links ul {
    list-style: image();
    padding: 15;
    margin: 10;
  }
  
  .footer-links li {
    margin: 5px 0;
  }
  
  .footer-links a {
    text-decoration: none;
    color: rgb(63, 54, 54);
    transition: color 0.3s;
  }
  
  .footer-links a:hover {
    color: #66bfff;
  }
  
  .footer-social {
    display: flex;
    align-items: center;
    color: #66bfff;
  }
  
  .footer-social a {
    text-decoration: none;
    color: white;
    margin-right: 10px;
    font-size: 20px;
  }
  
  .footer-social a:hover {
    color: #66bfff;
  }
  
  .footer-copyright {
    text-align: end;
    padding-top: 120px;
  }
  .horizontal-links {
  display: flex;
  justify-content: space-between; /* จัดตัวปุ่มทั้ง 3 ด้านหน้า, กลาง, ด้านหลัง */
  list-style: none; /* ลบขีดเส้นรายการ (bullets) ออก */
  padding: 0; /* ลบการระยะห่างของรายการ */
}

.horizontal-links li {
  margin: 0 20px; /* ระยะห่างระหว่างปุ่ม */
}

.footer-content {
  display: flex;
  align-items: center; /* จัดให้เนื้อหาตรงกลางตามแนวดิ่ง */
}
  </style>
  