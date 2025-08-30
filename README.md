<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Company Profile</title>
    <style>
        /* General */
        
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
        }
        /* Navbar */
        
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: #333;
            color: white;
            padding: 10px 20px;
        }
        
        nav ul {
            display: flex;
            list-style: none;
            margin: 0;
            padding: 0;
        }
        
        nav ul li {
            margin-left: 20px;
        }
        
        nav ul li a {
            color: white;
            text-decoration: none;
        }
        
        nav ul li a:hover {
            text-decoration: underline;
        }
        /* Banner */
        
        .banner {
            text-align: center;
            padding: 50px;
            background: #f4f4f4;
        }
        /* Profile Section */
        
        .profile {
            padding: 40px;
            background: #fff;
        }
        
        .profile-content {
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
        }
        
        .card {
            background: #f9f9f9;
            padding: 20px;
            margin: 10px;
            width: 30%;
            border-radius: 10px;
            box-shadow: 0px 0px 5px rgba(0, 0, 0, 0.1);
        }
        
        .card h3 {
            margin-top: 0;
        }
        /* Headquarters */
        
        .headquarters {
            background: #eee;
            text-align: center;
            padding: 40px;
        }
        
        .locations {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-top: 20px;
        }
        
        .circle {
            width: 100px;
            height: 100px;
            border-radius: 50%;
            background: white;
            display: flex;
            justify-content: center;
            align-items: center;
            box-shadow: 0px 0px 5px rgba(0, 0, 0, 0.2);
        }
        /* Message Form */
        
        .message-form {
            padding: 40px;
            background: #fff;
        }
        
        form {
            display: flex;
            flex-direction: column;
            width: 300px;
            margin: auto;
        }
        
        form label {
            margin-top: 10px;
        }
        
        form input,
        form textarea {
            padding: 8px;
            margin-top: 5px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        
        form button {
            margin-top: 15px;
            padding: 10px;
            border: none;
            background: #333;
            color: white;
            border-radius: 5px;
            cursor: pointer;
        }
        
        form button:hover {
            background: #555;
        }
        /* Output Box */
        
        #output {
            margin-top: 20px;
            padding: 15px;
            border: 1px solid #ddd;
            background: #f9f9f9;
            width: 300px;
            margin-left: auto;
            margin-right: auto;
        }
        /* Footer */
        
        footer {
            background: #333;
            color: white;
            text-align: center;
            padding: 15px;
            margin-top: 20px;
        }
        /* Responsive */
        
        @media (max-width: 768px) {
            .profile-content {
                flex-direction: column;
                align-items: center;
            }
            .card {
                width: 90%;
            }
            .locations {
                flex-direction: column;
            }
        }
    </style>
</head>

<body>
    <!-- Navbar -->
    <nav>
        <h1>My Website</h1>
        <ul>
            <li><a href="#home">Home</a></li>
            <li><a href="#profile">Our Profile</a></li>
            <li><a href="#products">Products</a></li>
            <li><a href="#message">Message Us</a></li>
        </ul>
    </nav>

    <!-- Home Section -->
    <section id="home" class="banner">
        <h2 id="welcomeText">Hi , Welcome To Website</h2>
        <p>Ini adalah website sederhana perusahaan.</p>
    </section>

    <!-- Our Profile Section -->
    <section id="profile" class="profile">
        <h2>Our Profile</h2>
        <div class="profile-content">
            <div class="card">
                <h3>About Company</h3>
                <p>Perusahaan kami bergerak di bidang teknologi inovatif...</p>
            </div>
            <div class="card">
                <h3>Vision</h3>
                <p>Menjadi perusahaan terdepan dalam solusi digital global.</p>
            </div>
            <div class="card">
                <h3>Mission</h3>
                <p>Memberikan layanan terbaik dan inovasi tanpa batas.</p>
            </div>
        </div>
    </section>

    <!-- Headquarters Section -->
    <section id="products" class="headquarters">
        <h2>Our Headquarters</h2>
        <div class="locations">
            <div class="circle">Jakarta</div>
            <div class="circle">Bandung</div>
            <div class="circle">Surabaya</div>
        </div>
    </section>

    <!-- Message Us Section -->
    <section id="message" class="message-form">
        <h2>Message Us</h2>
        <form id="contactForm">
            <label for="name">Name:</label>
            <input type="text" id="name" placeholder="Enter your name" required>

            <label for="email">Email:</label>
            <input type="email" id="email" placeholder="Enter your email" required>

            <label for="phone">Phone Number:</label>
            <input type="text" id="phone" placeholder="Enter your phone number" required>

            <label for="msg">Message:</label>
            <textarea id="msg" rows="4" placeholder="Enter your message" required></textarea>

            <button type="submit">Submit</button>
        </form>

        <div id="output"></div>
    </section>

    <footer>
        <p>Created by [Your Name]</p>
    </footer>

    <script>
        // Ganti nama otomatis di Home
        window.onload = function() {
            const userName = prompt("Masukkan nama Anda:");
            if (userName) {
                document.getElementById("welcomeText").innerText = `Hi ${userName}, Welcome To Website`;
            }
        };

        // Form validation & tampilkan hasil
        document.getElementById("contactForm").addEventListener("submit", function(event) {
            event.preventDefault();

            let name = document.getElementById("name").value;
            let email = document.getElementById("email").value;
            let phone = document.getElementById("phone").value;
            let message = document.getElementById("msg").value;

            if (name === "" || email === "" || phone === "" || message === "") {
                alert("Semua field wajib diisi!");
                return;
            }

            let output = `
        <h3>Message Received</h3>
        <p><b>Name:</b> ${name}</p>
        <p><b>Email:</b> ${email}</p>
        <p><b>Phone:</b> ${phone}</p>
        <p><b>Message:</b> ${message}</p>
      `;

            document.getElementById("output").innerHTML = output;

            document.getElementById("contactForm").reset();
        });
    </script>
</body>

</html>
