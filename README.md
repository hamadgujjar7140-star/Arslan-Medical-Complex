<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Arslan Medical Complex - Healthcare Excellence</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary-blue: #0078d4;
            --light-blue: #e3f2fd;
            --accent-blue: #2196f3;
            --water-blue: #00bcd4;
            --dark-blue: #005a9e;
            --dark-gray: #2c2c2c;
            --light-gray: #f5f5f5;
            --white: #ffffff;
            --shadow: rgba(0, 0, 0, 0.1);
            --text-dark: #333333;
            --text-light: #666666;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: var(--text-dark);
            background: linear-gradient(135deg, #e3f2fd 0%, #bbdefb 100%);
            min-height: 100vh;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header Styles */
        header {
            background: linear-gradient(135deg, var(--primary-blue) 0%, var(--dark-blue) 100%);
            color: var(--white);
            padding: 40px 20px;
            box-shadow: 0 4px 20px var(--shadow);
            position: relative;
            overflow: hidden;
        }

        header::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -10%;
            width: 500px;
            height: 500px;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 50%;
        }

        header::after {
            content: '';
            position: absolute;
            bottom: -30%;
            left: -5%;
            width: 400px;
            height: 400px;
            background: rgba(0, 188, 212, 0.1);
            border-radius: 50%;
        }

        .header-content {
            position: relative;
            z-index: 1;
        }

        h1 {
            font-size: 2.8em;
            margin-bottom: 10px;
            font-weight: 600;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.2);
        }

        .header-info {
            font-size: 1.1em;
            margin-top: 15px;
            opacity: 0.95;
        }

        .header-info p {
            margin: 5px 0;
        }

        .ceo-name {
            font-weight: 600;
            color: var(--water-blue);
        }

        /* Navigation */
        nav {
            background: var(--white);
            box-shadow: 0 2px 15px var(--shadow);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        nav ul {
            list-style: none;
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            padding: 0;
        }

        nav li {
            margin: 0;
        }

        nav a {
            display: block;
            padding: 18px 30px;
            text-decoration: none;
            color: var(--text-dark);
            font-weight: 500;
            transition: all 0.3s ease;
            position: relative;
        }

        nav a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 0;
            height: 3px;
            background: linear-gradient(90deg, var(--primary-blue), var(--water-blue));
            transition: width 0.3s ease;
        }

        nav a:hover {
            color: var(--primary-blue);
        }

        nav a:hover::after {
            width: 80%;
        }

        /* Section Styles */
        section {
            background: var(--white);
            margin: 40px auto;
            padding: 60px 40px;
            border-radius: 20px;
            box-shadow: 0 10px 40px var(--shadow);
            max-width: 1200px;
        }

        h2 {
            font-size: 2.5em;
            margin-bottom: 30px;
            color: var(--primary-blue);
            position: relative;
            display: inline-block;
        }

        h2::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 60px;
            height: 4px;
            background: linear-gradient(90deg, var(--water-blue), transparent);
            border-radius: 2px;
        }

        /* Team Section */
        .team-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
            margin-top: 40px;
        }

        .doctor-card {
            background: linear-gradient(135deg, var(--light-blue) 0%, var(--white) 100%);
            border-radius: 15px;
            padding: 30px;
            text-align: center;
            transition: all 0.4s ease;
            box-shadow: 0 5px 20px var(--shadow);
            border: 2px solid transparent;
        }

        .doctor-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(33, 150, 243, 0.3);
            border-color: var(--water-blue);
        }

        .doctor-photo {
            width: 150px;
            height: 150px;
            background: linear-gradient(135deg, var(--primary-blue), var(--water-blue));
            border-radius: 50%;
            margin: 0 auto 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 3.5em;
            color: var(--white);
            box-shadow: 0 5px 20px rgba(33, 150, 243, 0.4);
            overflow: hidden;
            border: 5px solid var(--white);
        }

        .doctor-photo img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: none;
        }

        .doctor-photo img.loaded {
            display: block;
        }

        .doctor-card h3 {
            font-size: 1.5em;
            color: var(--primary-blue);
            margin-bottom: 10px;
        }

        .doctor-card .specialty {
            color: var(--water-blue);
            font-weight: 600;
            font-size: 1.1em;
            margin-bottom: 15px;
        }

        .doctor-card p {
            color: var(--text-light);
            font-size: 0.95em;
        }

        /* Services Section */
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 25px;
            margin-top: 40px;
        }

        .service-card {
            background: linear-gradient(135deg, var(--white) 0%, var(--light-blue) 100%);
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 5px 15px var(--shadow);
            transition: all 0.3s ease;
            border-left: 4px solid var(--water-blue);
        }

        .service-card:hover {
            transform: translateX(10px);
            box-shadow: 0 8px 25px rgba(33, 150, 243, 0.2);
        }

        .service-icon {
            font-size: 2.5em;
            margin-bottom: 15px;
        }

        .service-card h3 {
            color: var(--primary-blue);
            margin-bottom: 10px;
            font-size: 1.3em;
        }

        .service-card p {
            color: var(--text-light);
            font-size: 0.95em;
        }

        /* Appointment Form */
        .appointment-wrapper {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 30px;
            margin-top: 30px;
        }

        .form-container {
            background: linear-gradient(135deg, var(--light-blue) 0%, var(--white) 100%);
            padding: 40px;
            border-radius: 15px;
            box-shadow: 0 5px 20px var(--shadow);
        }

        .appointment-info {
            background: linear-gradient(135deg, var(--primary-blue), var(--dark-blue));
            color: var(--white);
            padding: 40px;
            border-radius: 15px;
            box-shadow: 0 5px 20px var(--shadow);
            display: flex;
            flex-direction: column;
            justify-content: center;
        }

        .appointment-info h3 {
            font-size: 1.8em;
            margin-bottom: 20px;
            color: var(--white);
        }

        .appointment-info p {
            margin-bottom: 15px;
            font-size: 1.05em;
            line-height: 1.7;
        }

        .info-item {
            display: flex;
            align-items: center;
            margin-bottom: 15px;
            padding: 15px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
        }

        .info-item span {
            font-size: 1.5em;
            margin-right: 15px;
        }

        .form-group {
            margin-bottom: 20px;
        }

        label {
            display: block;
            margin-bottom: 8px;
            color: var(--primary-blue);
            font-weight: 600;
            font-size: 1em;
        }

        input, select, textarea {
            width: 100%;
            padding: 12px 15px;
            border: 2px solid #e0e0e0;
            border-radius: 10px;
            font-size: 0.95em;
            font-family: inherit;
            transition: all 0.3s ease;
            background: var(--white);
        }

        input:focus, select:focus, textarea:focus {
            outline: none;
            border-color: var(--water-blue);
            box-shadow: 0 0 0 3px rgba(0, 188, 212, 0.1);
        }

        textarea {
            resize: vertical;
            min-height: 80px;
        }

        .btn {
            background: linear-gradient(135deg, var(--primary-blue), var(--water-blue));
            color: var(--white);
            padding: 12px 30px;
            border: none;
            border-radius: 10px;
            font-size: 1em;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 5px 20px rgba(33, 150, 243, 0.4);
            width: 100%;
        }

        .btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(33, 150, 243, 0.5);
        }

        .btn:active {
            transform: translateY(0);
        }

        /* About Section */
        .about-content {
            font-size: 1.1em;
            line-height: 1.8;
            color: var(--text-light);
            margin-top: 30px;
        }

        .about-content p {
            margin-bottom: 20px;
        }

        .mission-vision {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
            margin-top: 40px;
        }

        .mission-box {
            background: linear-gradient(135deg, var(--light-blue) 0%, var(--white) 100%);
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 5px 15px var(--shadow);
            border-top: 4px solid var(--water-blue);
        }

        .mission-box h3 {
            color: var(--primary-blue);
            margin-bottom: 15px;
            font-size: 1.5em;
        }

        .mission-box p {
            color: var(--text-light);
        }

        /* Location Section */
        .location-section {
            background: linear-gradient(135deg, var(--primary-blue) 0%, var(--dark-blue) 100%);
            color: var(--white);
            padding: 60px 40px;
            border-radius: 20px;
            box-shadow: 0 10px 40px var(--shadow);
            margin: 40px auto;
            max-width: 1200px;
        }

        .location-section h2 {
            color: var(--white);
        }

        .location-section h2::after {
            background: linear-gradient(90deg, var(--water-blue), transparent);
        }

        .location-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            margin-top: 40px;
        }

        .location-info {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }

        .location-card {
            background: rgba(255, 255, 255, 0.1);
            padding: 25px;
            border-radius: 15px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            transition: all 0.3s ease;
        }

        .location-card:hover {
            background: rgba(255, 255, 255, 0.15);
            transform: translateX(10px);
        }

        .location-card h3 {
            font-size: 1.3em;
            margin-bottom: 10px;
            color: var(--water-blue);
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .location-card p {
            line-height: 1.7;
            opacity: 0.95;
        }

        .map-container {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            overflow: hidden;
            border: 2px solid rgba(255, 255, 255, 0.2);
            height: 400px;
            display: flex;
            align-items: center;
            justify-content: center;
            backdrop-filter: blur(10px);
        }

        .map-placeholder {
            text-align: center;
            color: var(--white);
            opacity: 0.9;
        }

        .map-placeholder p {
            font-size: 3em;
            margin-bottom: 15px;
        }

        /* Footer */
        footer {
            background: linear-gradient(135deg, var(--dark-gray) 0%, #1a1a1a 100%);
            color: var(--white);
            padding: 40px 20px;
            text-align: center;
            margin-top: 60px;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
        }

        .footer-info {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-bottom: 30px;
            text-align: left;
        }

        .footer-section h3 {
            color: var(--water-blue);
            margin-bottom: 15px;
            font-size: 1.3em;
        }

        .footer-section p {
            margin: 8px 0;
            opacity: 0.9;
        }

        .footer-bottom {
            border-top: 1px solid rgba(255, 255, 255, 0.1);
            padding-top: 20px;
            margin-top: 20px;
            opacity: 0.8;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            h1 {
                font-size: 2em;
            }

            h2 {
                font-size: 1.8em;
            }

            section {
                padding: 40px 25px;
                margin: 20px;
            }

            nav ul {
                flex-direction: column;
            }

            nav a {
                padding: 15px;
                border-bottom: 1px solid var(--light-gray);
            }

            .form-container {
                padding: 25px;
            }

            .appointment-wrapper {
                grid-template-columns: 1fr;
            }

            .location-content {
                grid-template-columns: 1fr;
            }

            .map-container {
                height: 300px;
            }

            .footer-info {
                text-align: center;
            }
        }

        /* Animations */
        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        section {
            animation: fadeIn 0.8s ease;
        }

        @keyframes float {
            0%, 100% {
                transform: translateY(0px);
            }
            50% {
                transform: translateY(-10px);
            }
        }

        .service-icon {
            animation: float 3s ease-in-out infinite;
        }
    </style>
</head>
<body>
    <header>
        <div class="container header-content">
            <h1>🏥 Arslan Medical Complex</h1>
            <div class="header-info">
                <p>📍 Zeeshan Colony, Kamalia</p>
                <p>Chief Executive Officer: <span class="ceo-name">Muhammad Saeed Gujjar</span></p>
            </div>
        </div>
    </header>

    <nav>
        <ul>
            <li><a href="#home">Home</a></li>
            <li><a href="#team">Our Team</a></li>
            <li><a href="#services">Services</a></li>
            <li><a href="#appointment">Book Appointment</a></li>
            <li><a href="#about">About Us</a></li>
            <li><a href="#location">Location</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>

    <section id="team">
        <div class="container">
            <h2>Meet Our Medical Team</h2>
            <div class="team-grid">
                <div class="doctor-card">
                    <div class="doctor-photo">
                        <img src="dr-zeeshan.jpg" alt="Dr. Zeeshan Saeed" id="dr-zeeshan-img">
                        <span id="dr-zeeshan-icon">👨‍⚕️</span>
                    </div>
                    <h3>Dr. Zeeshan Saeed</h3>
                    <p class="specialty">Hospital Manager & Chief Physician</p>
                    <p>Leading our medical operations with expertise and dedication. Dr. Zeeshan ensures comprehensive healthcare delivery and maintains the highest standards of patient care throughout the hospital.</p>
                </div>

                <div class="doctor-card">
                    <div class="doctor-photo">
                        <img src="dr-ayesha.jpg" alt="Dr. Ayesha Zeeshan" id="dr-ayesha-img">
                        <span id="dr-ayesha-icon">👩‍⚕️</span>
                    </div>
                    <h3>Dr. Ayesha Zeeshan</h3>
                    <p class="specialty">Gynecology Specialist</p>
                    <p>Providing exceptional women's healthcare with compassion and expertise. Dr. Ayesha specializes in maternal health, reproductive care, and comprehensive gynecological services.</p>
                </div>
            </div>
        </div>
    </section>

    <section id="services">
        <div class="container">
            <h2>Our Medical Services</h2>
            <div class="services-grid">
                <div class="service-card">
                    <div class="service-icon">🏥</div>
                    <h3>General Medicine</h3>
                    <p>Comprehensive healthcare for all ages with experienced physicians available for consultations and treatments.</p>
                </div>

                <div class="service-card">
                    <div class="service-icon">👶</div>
                    <h3>Gynecology & Obstetrics</h3>
                    <p>Specialized care for women's health, pregnancy management, and maternal wellness programs.</p>
                </div>

                <div class="service-card">
                    <div class="service-icon">🚑</div>
                    <h3>Emergency Care</h3>
                    <p>24/7 emergency medical services with rapid response and critical care capabilities.</p>
                </div>

                <div class="service-card">
                    <div class="service-icon">🔬</div>
                    <h3>Diagnostic Services</h3>
                    <p>Modern laboratory and diagnostic facilities for accurate testing and timely results.</p>
                </div>

                <div class="service-card">
                    <div class="service-icon">💊</div>
                    <h3>Pharmacy</h3>
                    <p>Well-stocked pharmacy with quality medications and expert pharmaceutical guidance.</p>
                </div>

                <div class="service-card">
                    <div class="service-icon">🩺</div>
                    <h3>Health Checkups</h3>
                    <p>Preventive care packages and comprehensive health screening programs for early detection.</p>
                </div>
            </div>
        </div>
    </section>

    <section id="appointment">
        <div class="container">
            <h2>Book Your Appointment</h2>
            <div class="appointment-wrapper">
                <div class="form-container">
                    <form id="appointmentForm">
                        <div class="form-group">
                            <label for="name">Full Name *</label>
                            <input type="text" id="name" name="name" required placeholder="Enter your full name">
                        </div>

                        <div class="form-group">
                            <label for="phone">Phone Number *</label>
                            <input type="tel" id="phone" name="phone" required placeholder="Enter your contact number">
                        </div>

                        <div class="form-group">
                            <label for="email">Email Address</label>
                            <input type="email" id="email" name="email" placeholder="Enter your email (optional)">
                        </div>

                        <div class="form-group">
                            <label for="doctor">Select Doctor *</label>
                            <select id="doctor" name="doctor" required>
                                <option value="">Choose a doctor</option>
                                <option value="dr-zeeshan">Dr. Zeeshan Saeed - General Medicine</option>
                                <option value="dr-ayesha">Dr. Ayesha Zeeshan - Gynecology</option>
                            </select>
                        </div>

                        <div class="form-group">
                            <label for="date">Preferred Date *</label>
                            <input type="date" id="date" name="date" required>
                        </div>

                        <div class="form-group">
                            <label for="message">Additional Information</label>
                            <textarea id="message" name="message" placeholder="Brief description of your concern..."></textarea>
                        </div>

                        <button type="submit" class="btn">Book Appointment</button>
                    </form>
                </div>

                <div class="appointment-info">
                    <h3>Why Choose Us?</h3>
                    <p>Experience healthcare excellence with our dedicated team of professionals committed to your wellbeing.</p>
                    
                    <div class="info-item">
                        <span>⚡</span>
                        <div>
                            <strong>Quick Appointments</strong><br>
                            Same-day appointments available
                        </div>
                    </div>

                    <div class="info-item">
                        <span>👨‍⚕️</span>
                        <div>
                            <strong>Expert Doctors</strong><br>
                            Experienced medical professionals
                        </div>
                    </div>

                    <div class="info-item">
                        <span>🏥</span>
                        <div>
                            <strong>Modern Facilities</strong><br>
                            State-of-the-art medical equipment
                        </div>
                    </div>

                    <div class="info-item">
                        <span>💙</span>
                        <div>
                            <strong>Compassionate Care</strong><br>
                            Patient-centered approach
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="about">
        <div class="container">
            <h2>About Arslan Medical Complex</h2>
            <div class="about-content">
                <p>Arslan Medical Complex stands as a pillar of healthcare excellence in Zeeshan Colony, Kamalia. Under the visionary leadership of CEO Muhammad Saeed Gujjar, we have transformed into a trusted medical institution serving our community with dedication and compassion.</p>
                
                <p>Our state-of-the-art facility combines modern medical technology with personalized patient care, ensuring that every individual receives the attention and treatment they deserve. From routine checkups to specialized gynecological care, we provide comprehensive medical services designed to meet the diverse healthcare needs of our community.</p>
                
                <p>At Arslan Medical Complex, we believe in building lasting relationships with our patients. Our experienced medical team works collaboratively to deliver evidence-based treatments while maintaining the warmth and empathy that makes healthcare truly healing.</p>
            </div>

            <div class="mission-vision">
                <div class="mission-box">
                    <h3>🎯 Our Mission</h3>
                    <p>To provide accessible, high-quality healthcare services that improve the well-being of our community. We are committed to clinical excellence, compassionate care, and continuous improvement in medical practices.</p>
                </div>

                <div class="mission-box">
                    <h3>👁️ Our Vision</h3>
                    <p>To be the leading healthcare provider in the region, recognized for medical excellence, patient satisfaction, and innovative healthcare solutions that set new standards in community wellness.</p>
                </div>

                <div class="mission-box">
                    <h3>💙 Our Values</h3>
                    <p>Compassion, integrity, excellence, and respect guide everything we do. We treat every patient as family and ensure their comfort, dignity, and privacy throughout their healthcare journey.</p>
                </div>
            </div>
        </div>
    </section>

    <div class="location-section" id="location">
        <div class="container">
            <h2>📍 Find Us</h2>
            <div class="location-content">
                <div class="location-info">
                    <div class="location-card">
                        <h3>🏥 Address</h3>
                        <p>Arslan Medical Complex<br>
                        Zeeshan Colony<br>
                        Kamalia, Punjab, Pakistan</p>
                    </div>

                    <div class="location-card">
                        <h3>📞 Contact Numbers</h3>
                        <p>Emergency: Available 24/7<br>
                        Appointments: Call during working hours<br>
                        For queries: Contact our reception</p>
                    </div>

                    <div class="location-card">
                        <h3>🕒 Working Hours</h3>
                        <p>Monday - Friday: 8:00 AM - 8:00 PM<br>
                        Saturday: 9:00 AM - 6:00 PM<br>
                        Sunday: 10:00 AM - 4:00 PM<br>
                        Emergency: 24/7 Available</p>
                    </div>

                    <div class="location-card">
                        <h3>🚗 How to Reach</h3>
                        <p>Located in the heart of Zeeshan Colony, easily accessible from main Kamalia city. Public transport and parking facilities available.</p>
                    </div>
                </div>

                <div class="map-container">
                    <iframe 
                        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d54424.17982919577!2d72.63891!3d30.81897!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3922b7f6c6c6c6c7%3A0x6c6c6c6c6c6c6c6c!2sKamalia%2C%20Toba%20Tek%20Singh%20District%2C%20Punjab%2C%20Pakistan!5e0!3m2!1sen!2s!4v1234567890123!5m2!1sen!2s" 
                        width="100%" 
                        height="100%" 
                        style="border:0; border-radius: 15px;" 
                        allowfullscreen="" 
                        loading="lazy" 
                        referrerpolicy="no-referrer-when-downgrade">
                    </iframe>
                </div>
            </div>
        </div>
    </div>

    <footer id="contact">
        <div class="footer-content">
            <div class="footer-info">
                <div class="footer-section">
                    <h3>Contact Information</h3>
                    <p>📍 Zeeshan Colony, Kamalia</p>
                    <p>📞 Contact us for appointments</p>
                    <p>🕒 24/7 Emergency Services</p>
                </div>

                <div class="footer-section">
                    <h3>Quick Links</h3>
                    <p>Emergency Care</p>
                    <p>General Consultations</p>
                    <p>Gynecology Services</p>
                    <p>Health Checkups</p>
                </div>

                <div class="footer-section">
                    <h3>Hospital Hours</h3>
                    <p>Monday - Friday: 8:00 AM - 8:00 PM</p>
                    <p>Saturday: 9:00 AM - 6:00 PM</p>
                    <p>Sunday: 10:00 AM - 4:00 PM</p>
                    <p>Emergency: 24/7</p>
                </div>
            </div>

            <div class="footer-bottom">
                <p>&copy; 2025 Arslan Medical Complex. All Rights Reserved.</p>
                <p>Your Health, Our Priority</p>
            </div>
        </div>
    </footer>

    <script>
        // Form submission handler
        document.getElementById('appointmentForm').addEventListener('submit', function(e) {
            e.preventDefault();
            alert('Thank you for booking an appointment! Our team will contact you shortly to confirm your appointment details.');
            this.reset();
        });

        // Smooth scrolling for navigation links
        document.querySelectorAll('nav a').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                const targetId = this.getAttribute('href');
                if (targetId === '#home') {
                    window.scrollTo({ top: 0, behavior: 'smooth' });
                } else {
                    const target = document.querySelector(targetId);
                    if (target) {
                        target.scrollIntoView({ behavior: 'smooth', block: 'start' });
                    }
                }
            });
        });

        // Set minimum date for appointment to today
        const dateInput = document.getElementById('date');
        const today = new Date().toISOString().split('T')[0];
        dateInput.setAttribute('min', today);

        // Photo loading handler
        function loadDoctorPhoto(imgId, iconId) {
            const img = document.getElementById(imgId);
            const icon = document.getElementById(iconId);
            
            img.addEventListener('load', function() {
                this.classList.add('loaded');
                icon.style.display = 'none';
            });
            
            img.addEventListener('error', function() {
                console.log('Photo not found, displaying icon instead');
            });
        }

        loadDoctorPhoto('dr-zeeshan-img', 'dr-zeeshan-icon');
        loadDoctorPhoto('dr-ayesha-img', 'dr-ayesha-icon');
    </script>
</body>
</html>
