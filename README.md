<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>ستور الملوك - شحن الألعاب</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@400;600;700&display=swap" rel="stylesheet">
  <style>
    :root {
      --primary-color: #001f3f;
      --secondary-color: #0074D9;
      --accent-color: #FFD700;
      --dark-blue: #003366;
      --medium-blue: #00509E;
      --light-blue: #004080;
    }
    
    body {
      margin: 0;
      font-family: 'Cairo', sans-serif;
      background: linear-gradient(to bottom, var(--primary-color), var(--secondary-color));
      color: white;
      line-height: 1.6;
    }
    
    header {
      padding: 20px;
      text-align: center;
      background-color: var(--dark-blue);
      box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
    }
    
    header h1 {
      margin: 0;
      font-size: 2.5em;
      color: var(--accent-color);
    }
    
    nav {
      text-align: center;
      background-color: var(--medium-blue);
      padding: 12px 0;
      position: sticky;
      top: 0;
      z-index: 100;
    }
    
    nav a {
      color: white;
      margin: 0 15px;
      text-decoration: none;
      font-weight: bold;
      font-size: 1.1em;
      transition: color 0.3s;
    }
    
    nav a:hover {
      color: var(--accent-color);
    }
    
    .section {
      padding: 50px 20px;
      text-align: center;
      max-width: 1200px;
      margin: 0 auto;
    }
    
    .section h2 {
      font-size: 2em;
      margin-bottom: 30px;
      color: var(--accent-color);
    }
    
    .games {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
      gap: 25px;
      padding: 20px;
    }
    
    .game {
      background-color: var(--light-blue);
      padding: 20px;
      border-radius: 10px;
      cursor: pointer;
      transition: transform 0.3s, box-shadow 0.3s;
      font-weight: 600;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    }
    
    .game:hover {
      transform: translateY(-5px);
      box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
      background-color: #0055a5;
    }
    
    .hidden {
      display: none;
    }
    
    .form-popup {
      margin: 30px auto;
      padding: 30px;
      background-color: rgba(0, 64, 128, 0.9);
      border-radius: 15px;
      max-width: 500px;
      box-shadow: 0 8px 24px rgba(0, 0, 0, 0.3);
    }
    
    .prices-container {
      margin: 30px auto;
      padding: 20px;
      background-color: rgba(0, 64, 128, 0.9);
      border-radius: 15px;
      max-width: 800px;
      box-shadow: 0 8px 24px rgba(0, 0, 0, 0.3);
      text-align: right;
    }
    
    .price-table {
      width: 100%;
      border-collapse: collapse;
      margin-top: 20px;
    }
    
    .price-table th, .price-table td {
      padding: 12px;
      border-bottom: 1px solid rgba(255, 255, 255, 0.1);
    }
    
    .price-table th {
      background-color: rgba(255, 215, 0, 0.2);
      color: var(--accent-color);
    }
    
    footer {
      background-color: var(--primary-color);
      padding: 25px;
      text-align: center;
      margin-top: 40px;
    }
    
    .whatsapp-button {
      display: inline-block;
      margin-top: 20px;
      background-color: #25D366;
      color: white;
      padding: 12px 25px;
      text-decoration: none;
      font-size: 1.1em;
      border-radius: 5px;
      font-weight: bold;
      transition: background-color 0.3s, transform 0.2s;
    }
    
    .whatsapp-button:hover {
      background-color: #128C7E;
      transform: scale(1.05);
    }
    
    select, input[type="text"], button {
      font-size: 1em;
      padding: 12px;
      margin: 15px 0;
      width: 80%;
      max-width: 350px;
      border: none;
      border-radius: 8px;
      font-family: 'Cairo', sans-serif;
    }
    
    button {
      background-color: var(--accent-color);
      color: var(--primary-color);
      font-weight: bold;
      cursor: pointer;
      transition: background-color 0.3s;
    }
    
    button:hover {
      background-color: #ffc800;
    }
    
    input[type="text"]:focus, select:focus {
      outline: 2px solid var(--accent-color);
    }
    
    .payment-methods {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 20px;
      margin-top: 30px;
    }
    
    .payment-method {
      background-color: rgba(255, 255, 255, 0.1);
      padding: 15px 25px;
      border-radius: 8px;
      min-width: 150px;
    }
    
    .payment-method::before {
      content: "✅";
      margin-left: 8px;
    }
    
    .success-message {
      background-color: rgba(0, 200, 0, 0.2);
      padding: 20px;
      border-radius: 10px;
      margin: 20px auto;
      max-width: 500px;
      border: 1px solid #00aa00;
    }
    
    .phone-number {
      color: var(--accent-color);
      font-weight: bold;
      font-size: 1.1em;
      margin: 10px 0;
    }
    
    .action-buttons {
      display: flex;
      justify-content: center;
      gap: 15px;
      margin-top: 20px;
    }
    
    .action-button {
      padding: 10px 20px;
      border-radius: 8px;
      cursor: pointer;
      font-weight: bold;
      transition: all 0.3s;
    }
    
    .price-button {
      background-color: #4CAF50;
      color: white;
    }
    
    .order-button {
      background-color: var(--accent-color);
      color: var(--primary-color);
    }
    
    .action-button:hover {
      opacity: 0.9;
      transform: translateY(-2px);
    }
    
    @media (max-width: 768px) {
      .games {
        grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
      }
      
      nav a {
        margin: 0 10px;
        font-size: 1em;
      }
      
      .section {
        padding: 30px 15px;
      }
      
      .price-table {
        font-size: 0.9em;
      }
      
      .action-buttons {
        flex-direction: column;
        gap: 10px;
      }
    }
  </style>
</head>
<body>

<header>
  <h1>💎 ستور الملوك 💎</h1>
  <p>شحن جميع الألعاب بأسعار تنافسية وخدمة سريعة</p>
</header>

<nav>
  <a href="#games">الألعاب</a>
  <a href="#payment">طرق الدفع</a>
  <a href="#how-to-order">كيفية الطلب</a>
  <a href="#contact">تواصل معنا</a>
</nav>

<section id="games" class="section">
  <h2>🎮 الألعاب المتوفرة</h2>
  <p>اختر اللعبة التي تريد شحن رصيد لها</p>
  
  <div class="games">
    <div class="game" onclick="showGameOptions('pubg')">ببجي موبايل</div>
    <div class="game" onclick="showGameOptions('freefire')">فري فاير</div>
    <div class="game" onclick="showGameOptions('fortnite')">فورتنايت</div>
    <div class="game" onclick="showGameOptions('pes')">بيس 2025</div>
    <div class="game" onclick="showGameOptions('cod')">كول أوف ديوتي</div>
    <div class="game" onclick="showGameOptions('valorant')">فالورانت</div>
  </div>

  <div id="gameOptions" class="hidden">
    <div class="action-buttons">
      <button class="action-button price-button" onclick="showPrices()">عرض الأسعار</button>
      <button class="action-button order-button" onclick="showOrderForm()">تقديم طلب شحن</button>
    </div>
    
    <div id="pricesSection" class="prices-container hidden">
      <h3 id="pricesTitle">أسعار الشحن</h3>
      <div class="phone-number">رقم التحويل: <span>01229877018</span></div>
      <table class="price-table">
        <thead>
          <tr>
            <th>الباقة</th>
            <th>الكمية</th>
            <th>السعر</th>
          </tr>
        </thead>
        <tbody id="pricesTable">
          <!-- سيتم ملؤها بواسطة الجافاسكريبت -->
        </tbody>
      </table>
    </div>

    <div id="forms" class="form-popup hidden">
      <h3 id="gameTitle">ادخل الـ ID الخاص بك:</h3>
      <input type="text" id="gameIdInput" placeholder="مثال: 1234567890" required />
      <br/>
      <select id="paymentMethod" required>
        <option value="" disabled selected>اختر طريقة الدفع</option>
        <option value="vodafone">فودافون كاش (01229877018)</option>
        <option value="orange">أورنج كاش (01229877018)</option>
        <option value="etisalat">اتصالات كاش (01229877018)</option>
        <option value="we">وي باي</option>
        <option value="wenesa">ونيسا باي</option>
        <option value="visa">فيزا / ماستر كارد</option>
      </select>
      <div class="phone-number">رقم الهاتف للدفع: <span>01229877018</span></div>
      <br/>
      <button onclick="submitForm()">إرسال الطلب</button>
    </div>
  </div>
  
  <div id="successMessage" class="success-message hidden">
    <h3>تم إرسال طلبك بنجاح!</h3>
    <p id="successDetails"></p>
    <p>سنتصل بك خلال 15 دقيقة لتأكيد الطلب</p>
    <p class="phone-number">رقم الهاتف للاستفسار: <span>01229877018</span></p>
  </div>
</section>

<section id="payment" class="section">
  <h2>💳 طرق الدفع المتاحة</h2>
  <p>يمكنك الدفع بأي من الطرق التالية:</p>
  
  <div class="payment-methods">
    <div class="payment-method">فودافون كاش (01229877018)</div>
    <div class="payment-method">أورانج كاش (01229877018)</div>
    <div class="payment-method">اتصالات كاش (01229877018)</div>
    <div class="payment-method">وي باي (WE Pay)</div>
    <div class="payment-method">ونيسا باي</div>
    <div class="payment-method">فيزا / ماستر كارد</div>
  </div>
  
  <div class="phone-number" style="margin-top: 30px;">
    رقم الهاتف لجميع طرق الدفع: <span>01229877018</span>
  </div>
</section>

<section id="how-to-order" class="section">
  <h2>📝 كيفية الطلب</h2>
  <div style="text-align: right; max-width: 700px; margin: 0 auto;">
    <ol style="font-size: 1.1em; line-height: 2;">
      <li>اختر اللعبة من قائمة الألعاب المتاحة</li>
      <li>اضغط على "عرض الأسعار" لرؤية باقات الشحن المتاحة</li>
      <li>اضغط على "تقديم طلب شحن"</li>
      <li>أدخل الـ ID الخاص بك في اللعبة</li>
      <li>اختر طريقة الدفع المناسبة لك</li>
      <li>قم بالتحويل إلى الرقم <strong>01229877018</strong></li>
      <li>اضغط على زر "إرسال الطلب"</li>
      <li>سنقوم بالتواصل معك خلال دقائق لتأكيد الطلب</li>
      <li>بعد التحويل، سيتم شحن الرصيد فورًا لحسابك</li>
    </ol>
  </div>
</section>

<section id="contact" class="section">
  <h2>📞 تواصل معنا</h2>
  <p>للاستفسار أو المساعدة، راسلنا مباشرة عبر واتساب</p>
  <a class="whatsapp-button" href="https://wa.me/201229877018" target="_blank">
    <span style="margin-left: 8px;">💬</span> راسلنا على واتساب (01229877018)
  </a>
  
  <div style="margin-top: 30px;">
    <p>أوقات العمل: يوميًا من 10 صباحًا حتى 2 صباحًا</p>
    <p>رقم الهاتف: <strong>01229877018</strong></p>
    <p>البريد الإلكتروني: info@store-elmoulouk.com</p>
  </div>
</section>

<footer>
  <p>جميع الحقوق محفوظة &copy; ستور الملوك 2025</p>
  <p style="font-size: 0.9em; margin-top: 10px;">للدفع على الرقم: <strong>01229877018</strong></p>
</footer>

<script>
  // بيانات الألعاب والأسعار
  const gameData = {
    pubg: {
      title: "ببجي موبايل",
      prices: [
        { package: "شدادات UC", quantity: "60 UC", price: "10 جنيه" },
        { package: "شدادات UC", quantity: "325 UC", price: "50 جنيه" },
        { package: "شدادات UC", quantity: "660 UC", price: "100 جنيه" },
        { package: "شدادات UC", quantity: "1800 UC", price: "250 جنيه" },
        { package: "شدادات UC", quantity: "3850 UC", price: "500 جنيه" }
      ]
    },
    freefire: {
      title: "فري فاير",
      prices: [
        { package: "جواهر", quantity: "110 جوهرة", price: "5 جنيه" },
        { package: "جواهر", quantity: "231 جوهرة", price: "8 جنيه" },
        { package: "جواهر", quantity: "583 جوهرة", price: "19 جنيه" },
        { package: "جواهر", quantity: "1188 جوهرة", price: "41 جنيه" },
        { package: "جواهر", quantity: "2420 جوهرة", price: "80 جنيه" }
      ]
    },
    fortnite: {
      title: "فورتنايت",
      prices: [
        { package: "فيباكس", quantity: "1000 فيباكس", price: "70 جنيه" },
        { package: "فيباكس", quantity: "2800 فيباكس", price: "180 جنيه" },
        { package: "فيباكس", quantity: "5000 فيباكس", price: "300 جنيه" },
        { package: "فيباكس", quantity: "13500 فيباكس", price: "750 جنيه" }
      ]
    },
    pes: {
      title: "بيس 2025",
      prices: [
        {
