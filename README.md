<!DOCTYPE html>
<html lang="bn">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Safa Online Shop | Intelligent Talking Book</title>

<style>
body{
  margin:0;
  font-family: Arial, sans-serif;
  background:#f8f9fa;
  color:#222;
}
.container{
  max-width:1100px;
  margin:auto;
  padding:20px;
}
.hero{
  background:linear-gradient(135deg,#d1004b,#ff5c8a);
  color:#fff;
  padding:50px 20px;
  text-align:center;
}
.hero h1{font-size:32px;margin-bottom:10px;}
.hero p{font-size:18px;}

.price{
  font-size:28px;
  font-weight:bold;
  margin:15px 0;
}

.btn{
  background:#fff;
  color:#d1004b;
  padding:12px 25px;
  border-radius:30px;
  text-decoration:none;
  font-weight:bold;
  display:inline-block;
  margin-top:15px;
}

.section{
  background:#fff;
  margin-top:30px;
  padding:30px;
  border-radius:12px;
  box-shadow:0 5px 15px rgba(0,0,0,.08);
}

.features li{
  margin-bottom:10px;
  font-size:16px;
}

.payment-form label{
  display:block;
  margin-top:12px;
  font-weight:bold;
}
.payment-form input,
.payment-form textarea,
.payment-form select{
  width:100%;
  padding:10px;
  margin-top:6px;
  border-radius:6px;
  border:1px solid #ccc;
}
.payment-form button{
  width:100%;
  margin-top:18px;
  background:#d1004b;
  color:#fff;
  padding:12px;
  border:none;
  border-radius:6px;
  font-size:16px;
  font-weight:bold;
}

footer{
  text-align:center;
  padding:20px;
  font-size:14px;
  color:#666;
}
</style>
</head>

<body>

<!-- HERO -->
<section class="hero">
  <h1>Intelligent Talking Book</h1>
  <p>বাচ্চাদের শেখার সেরা স্মার্ট বই</p>
  <div class="price">৳ 999</div>
  <a href="#order" class="btn">অর্ডার করুন</a>
</section>

<div class="container">

<!-- FEATURES -->
<section class="section">
  <h2>📘 কেন এই বইটি কিনবেন?</h2>
  <ul class="features">
    <li>✅ ইংরেজি, বাংলা, নাম্বার শেখা</li>
    <li>✅ বাচ্চাদের মেধা বিকাশে সহায়ক</li>
    <li>✅ সম্পূর্ণ Safe & Battery Operated</li>
    <li>✅ ৩–৮ বছর বয়সী শিশুদের জন্য উপযুক্ত</li>
  </ul>
</section>

<!-- PAYMENT FORM -->
<section id="order" class="section payment-form">
  <h2>🧾 অর্ডার ও পেমেন্ট তথ্য</h2>

  <form onsubmit="sendOrder(event)">
    <input type="hidden" id="orderId">

    <label>আপনার নাম</label>
    <input type="text" id="name" required>

    <label>মোবাইল নাম্বার</label>
    <input type="tel" id="phone" required>

    <label>bKash Transaction ID</label>
    <input type="text" id="trxid" required>

    <label>ঠিকানা</label>
    <textarea id="address" required></textarea>

    <label>ডেলিভারি লোকেশন</label>
    <select id="delivery" onchange="calcTotal()" required>
      <option value="">সিলেক্ট করুন</option>
      <option value="60">ঢাকার ভিতরে (৳60)</option>
      <option value="120">ঢাকার বাইরে (৳120)</option>
    </select>

    <p><strong>মোট টাকা: ৳ <span id="total">999</span></strong></p>

    <button type="submit">✅ অর্ডার কনফার্ম করুন</button>
  </form>
</section>

</div>

<footer>
  © 2026 Safa Online Shop | Developed by Sojib
</footer>

<script>
const basePrice = 999;
const orderId = "ORD-" + Math.floor(100000 + Math.random()*900000);
document.getElementById("orderId").value = orderId;

function calcTotal(){
  const d = document.getElementById("delivery").value;
  document.getElementById("total").innerText = basePrice + Number(d || 0);
}

function sendOrder(e){
  e.preventDefault();

  const msg =
  "New Order%0A"+
  "Order ID: "+orderId+"%0A"+
  "Name: "+name.value+"%0A"+
  "Phone: "+phone.value+"%0A"+
  "TrxID: "+trxid.value+"%0A"+
  "Address: "+address.value+"%0A"+
  "Total: ৳"+total.innerText;

  window.open(
    "https://wa.me/8801XXXXXXXXX?text="+msg,
    "_blank"
  );
}
</script>

</body>
</html>
