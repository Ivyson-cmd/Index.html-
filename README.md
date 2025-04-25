# Index.html-<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>FixPoint | Phone Repair & Electrical Solutions</title>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;800&display=swap" rel="stylesheet">
  <style>
    body {
      margin: 0;
      font-family: 'Inter', sans-serif;
      background: #ffffff;
      color: #333;
      overflow-x: hidden;
    }

    header {
      background: #141414;
      color: white;
      padding: 2rem;
      text-align: center;
      animation: fadeInDown 1s ease-in-out;
    }

    nav {
      background: #f8f8f8;
      display: flex;
      justify-content: center;
      gap: 2rem;
      padding: 1rem;
      box-shadow: 0 2px 6px rgba(0,0,0,0.05);
    }

    nav a {
      text-decoration: none;
      color: #222;
      font-weight: 600;
      transition: color 0.3s;
    }

    nav a:hover {
      color: #EF476F;
    }

    .hero {
      display: flex;
      flex-direction: column;
      align-items: center;
      text-align: center;
      padding: 3rem 2rem;
      background: #fff7f7;
      animation: fadeIn 1.2s ease-in;
    }

    .hero img {
      max-width: 100%;
      height: auto;
      border-radius: 10px;
      margin-top: 1rem;
    }

    section {
      max-width: 1000px;
      margin: 2rem auto;
      padding: 1rem;
    }

    .service {
      background: #f1f1f1;
      padding: 1rem;
      margin-bottom: 1.5rem;
      border-radius: 10px;
      transition: transform 0.3s ease-in-out;
    }

    .service:hover {
      transform: scale(1.02);
    }

    .booking-form {
      background: #fefefe;
      padding: 2rem;
      border-radius: 10px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.05);
    }

    label, select, input {
      display: block;
      width: 100%;
      margin-bottom: 1rem;
      padding: 0.5rem;
      font-size: 1rem;
    }

    button {
      background: #EF476F;
      color: white;
      padding: 0.75rem;
      border: none;
      border-radius: 5px;
      font-weight: bold;
      cursor: pointer;
      transition: background 0.3s;
    }

    button:hover {
      background: #d64060;
    }

    footer {
      text-align: center;
      padding: 2rem;
      background: #141414;
      color: white;
      margin-top: 3rem;
    }

    @keyframes fadeIn {
      0% { opacity: 0; transform: translateY(20px); }
      100% { opacity: 1; transform: translateY(0); }
    }

    @keyframes fadeInDown {
      0% { opacity: 0; transform: translateY(-20px); }
      100% { opacity: 1; transform: translateY(0); }
    }

    .image-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 1rem;
      margin-top: 2rem;
    }

    .image-grid img {
      width: 100%;
      border-radius: 10px;
      height: 200px;
      object-fit: cover;
    }
  </style>
</head>
<body>
  <header>
    <h1>FixPoint</h1>
    <p>Your Go-To for Phone Repairs & Electrical Work</p>
  </header>

  <nav>
    <a href="#services">Services</a>
    <a href="#book">Book</a>
    <a href="#contact">Contact</a>
  </nav>

  <section class="hero">
    <h1>Fast, Affordable & Trusted Technicians</h1>
    <p>Professional phone repair and home electrical solutions at your convenience.</p>
    <img src="https://images.unsplash.com/photo-1611210620004-b99d88c9b9fd" alt="Repair tech">
  </section>

  <section id="services">
    <h2>Our Services</h2>
    <div class="service">
      <h3>Phone Repair</h3>
      <p>Cracked screens, water damage, slow charging – we fix it all, on-site or at your location.</p>
    </div>
    <div class="service">
      <h3>Electrical Installations</h3>
      <p>Safe wiring, lighting, sockets, and full maintenance. Certified and insured electricians.</p>
    </div>
    <div class="image-grid">
      <img src="https://images.unsplash.com/photo-1603791440384-56cd371ee9a7" alt="Phone repair">
      <img src="https://images.unsplash.com/photo-1605902711622-cfb43c4437d1" alt="Electrician working">
      <img src="https://images.unsplash.com/photo-1581090700227-1c9a14f0c798" alt="Wiring tools">
    </div>
  </section>

  <section id="book">
    <h2>Book an Appointment</h2>
    <form class="booking-form" id="bookingForm">
      <label for="service">Select Service</label>
      <select id="service" required>
        <option value="">-- Choose a service --</option>
        <option value="phone">Phone Repair</option>
        <option value="electrical">Electrical Work</option>
      </select>

      <label for="location">Your Location</label>
      <select id="location" required>
        <option value="">-- Choose your location --</option>
        <option value="urban">Urban (KES 500)</option>
        <option value="suburban">Suburban (KES 700)</option>
        <option value="rural">Rural (KES 1000)</option>
      </select>

      <label for="date">Preferred Date</label>
      <input type="date" id="date" required>

      <p id="feeDisplay">Booking Fee: KES 0</p>

      <button type="submit">Book Now</button>
    </form>
  </section>

  <section id="contact">
    <h2>Contact Us</h2>
    <p>Email: info@fixpoint.co.ke</p>
    <p>Phone: +254 712 345 678</p>
  </section>

  <footer>
    <p>&copy; 2025 FixPoint. All rights reserved.</p>
  </footer>

  <script>
    const locationSelect = document.getElementById("location");
    const feeDisplay = document.getElementById("feeDisplay");

    locationSelect.addEventListener("change", function () {
      const value = this.value;
      let fee = 0;
      if (value === "urban") fee = 500;
      else if (value === "suburban") fee = 700;
      else if (value === "rural") fee = 1000;
      feeDisplay.textContent = "Booking Fee: KES " + fee;
    });

    document.getElementById("bookingForm").addEventListener("submit", function (e) {
      e.preventDefault();
      alert("Thank you! Your appointment has been booked.");
    });
  </script>
</body>
</html>
