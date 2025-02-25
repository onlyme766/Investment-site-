<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>ইনভেস্টমেন্ট সাইট - এডমিন প্যানেল</title>
  <style>
    /* সাধারণ স্টাইল */
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
      line-height: 1.6;
      color: #333;
    }

    .container {
      width: 90%;
      margin: auto;
      overflow: hidden;
    }

    /* হেডার */
    header {
      background: #333;
      color: #fff;
      padding: 10px 0;
    }

    header h1 {
      float: left;
    }

    nav {
      float: right;
    }

    nav ul {
      margin: 0;
      padding: 0;
      list-style: none;
    }

    nav ul li {
      display: inline;
      margin-left: 20px;
    }

    nav ul li a {
      color: #fff;
      text-decoration: none;
    }

    /* হিরো সেকশন */
    .hero {
      background: url('https://via.placeholder.com/1200x400') no-repeat center center/cover;
      color: #fff;
      padding: 100px 0;
      text-align: center;
    }

    .hero h2 {
      font-size: 2.5em;
    }

    .hero p {
      font-size: 1.2em;
    }

    .hero .btn {
      background: #28a745;
      color: #fff;
      padding: 10px 20px;
      text-decoration: none;
      border-radius: 5px;
    }

    /* এডমিন প্যানেল */
    .admin-panel {
      display: none;
      padding: 20px;
      background: #f4f4f4;
      margin-top: 20px;
    }

    .admin-panel h2 {
      margin-bottom: 20px;
    }

    .admin-panel table {
      width: 100%;
      border-collapse: collapse;
    }

    .admin-panel table th, .admin-panel table td {
      border: 1px solid #ddd;
      padding: 8px;
      text-align: left;
    }

    .admin-panel table th {
      background: #333;
      color: #fff;
    }

    /* ফর্ম স্টাইল */
    form {
      margin-bottom: 20px;
    }

    form input, form textarea {
      width: 100%;
      padding: 10px;
      margin-bottom: 10px;
      border-radius: 5px;
      border: 1px solid #ddd;
    }

    form button {
      background: #28a745;
      color: #fff;
      padding: 10px 20px;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }

    /* ফুটার */
    footer {
      background: #222;
      color: #fff;
      text-align: center;
      padding: 20px 0;
      margin-top: 20px;
    }
  </style>
</head>
<body>
  <header>
    <div class="container">
      <h1>ইনভেস্টমেন্ট সাইট</h1>
      <nav>
        <ul>
          <li><a href="#home">হোম</a></li>
          <li><a href="#admin-login">এডমিন লগইন</a></li>
        </ul>
      </nav>
    </div>
  </header>

  <section id="home" class="hero">
    <div class="container">
      <h2>আপনার ভবিষ্যতের জন্য সঠিক ইনভেস্টমেন্ট</h2>
      <p>আমাদের সাথে শুরু করুন এবং আপনার আর্থিক লক্ষ্য অর্জন করুন।</p>
      <a href="#payment" class="btn">পেমেন্ট করুন</a>
    </div>
  </section>

  <section id="payment" class="payment">
    <div class="container">
      <h2>পেমেন্ট</h2>
      <form id="payment-form">
        <label for="amount">পরিমাণ:</label>
        <input type="number" id="amount" required>
        <br>
        <label for="phone">ফোন নম্বর:</label>
        <input type="text" id="phone" required>
        <br>
        <label for="transactionId">ট্রানজেকশন আইডি:</label>
        <input type="text" id="transactionId" required>
        <br>
        <button type="submit">পেমেন্ট করুন</button>
      </form>
    </div>
  </section>

  <section id="admin-login" class="admin-login">
    <div class="container">
      <h2>এডমিন লগইন</h2>
      <form id="login-form">
        <label for="username">ইউজারনেম:</label>
        <input type="text" id="username" required>
        <br>
        <label for="password">পাসওয়ার্ড:</label>
        <input type="password" id="password" required>
        <br>
        <button type="submit">লগইন</button>
      </form>
    </div>
  </section>

  <section id="admin-panel" class="admin-panel">
    <div class="container">
      <h2>এডমিন প্যানেল</h2>
      <table id="payment-data">
        <thead>
          <tr>
            <th>পরিমাণ</th>
            <th>ফোন নম্বর</th>
            <th>ট্রানজেকশন আইডি</th>
          </tr>
        </thead>
        <tbody>
          <!-- ডেটা এখানে যোগ হবে -->
        </tbody>
      </table>
    </div>
  </section>

  <footer>
    <div class="container">
      <p>&copy; ২০২৫ ইনভেস্টমেন্ট সাইট। সকল অধিকার সংরক্ষিত।</p>
    </div>
  </footer>

  <script>
    // ডেটা সংরক্ষণের জন্য LocalStorage ব্যবহার করুন
    if (!localStorage.getItem('payments')) {
      localStorage.setItem('payments', JSON.stringify([]));
    }

    // পেমেন্ট ফর্ম সাবমিট হ্যান্ডলার
    document.getElementById('payment-form').addEventListener('submit', function (e) {
      e.preventDefault();

      const amount = document.getElementById('amount').value;
      const phone = document.getElementById('phone').value;
      const transactionId = document.getElementById('transactionId').value;

      const paymentData = {
        amount,
        phone,
        transactionId,
      };

      // LocalStorage-এ ডেটা সংরক্ষণ করুন
      const payments = JSON.parse(localStorage.getItem('payments'));
      payments.push(paymentData);
      localStorage.setItem('payments', JSON.stringify(payments));

      alert('পেমেন্ট সফল!');
      document.getElementById('payment-form').reset();
    });

    // এডমিন লগইন ফর্ম সাবমিট হ্যান্ডলার
    document.getElementById('login-form').addEventListener('submit', function (e) {
      e.preventDefault();

      const username = document.getElementById('username').value;
      const password = document.getElementById('password').value;

      // মক লগইন (ইউজারনেম: admin, পাসওয়ার্ড: 1234)
      if (username === 'admin' && password === '1234') {
        document.getElementById('admin-login').style.display = 'none';
        document.getElementById('admin-panel').style.display = 'block';
        loadPaymentData();
      } else {
        alert('ভুল ইউজারনেম বা পাসওয়ার্ড!');
      }
    });

    // পেমেন্ট ডেটা লোড করুন
    function loadPaymentData() {
      const payments = JSON.parse(localStorage.getItem('payments'));
      const tableBody = document.querySelector('#payment-data tbody');
      tableBody.innerHTML = '';

      payments.forEach(payment => {
        const row = document.createElement('tr');
        row.innerHTML = `
          <td>${payment.amount}</td>
          <td>${payment.phone}</td>
          <td>${payment.transactionId}</td>
        `;
        tableBody.appendChild(row);
      });
    }
  </script>
</body>
</html>