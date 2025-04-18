# CSS Layouts and Responsive Design

## Objectives

Implement Flexbox and Grid for layout design.
Make the webpage responsive using media queries.
Ensure proper alignment and spacing.

## Instructions

- use Flexbox or CSS Grid.
- Add a navigation bar and structure the content.
- Use media queries to adjust layout for mobile, tablet, and desktop.

>[!NOTE]
>  - Include at least:
>  - navigation bar
>  - media queries

# Tasks

- Apply Flexbox or Grid for layout.
- Make the page responsive.
- Test across different screen sizes.
ASSIGNEMENT
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Safe Space Kenya - Professional Counseling Services</title>
    <style>
        /* Reset and base styles */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Arial', sans-serif;
            line-height: 1.6;
            color: #333;
            background-color: #f5f9fc;
        }
        
        /* Navigation - Flexbox */
        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background-color: #1a5276;
            padding: 1rem 2rem;
            color: white;
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            color: white;
        }
        
        .nav-links {
            display: flex;
            list-style: none;
        }
        
        .nav-links li {
            margin-left: 1.5rem;
        }
        
        .nav-links a {
            color: white;
            text-decoration: none;
            transition: color 0.3s;
            font-weight: 500;
        }
        
        .nav-links a:hover {
            color: #aed6f1;
        }
        
        /* Employee Login Button */
        .employee-login {
            background-color: #f39c12;
            padding: 0.5rem 1rem;
            border-radius: 5px;
            margin-left: 1.5rem;
        }
        
        .employee-login:hover {
            background-color: #e67e22;
            color: white;
        }
        
        /* Login Modal */
        .modal {
            display: none;
            position: fixed;
            z-index: 1000;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0,0,0,0.5);
        }
        
        .modal-content {
            background-color: white;
            margin: 10% auto;
            padding: 2rem;
            border-radius: 8px;
            width: 90%;
            max-width: 400px;
            box-shadow: 0 4px 8px rgba(0,0,0,0.2);
        }
        
        .close-btn {
            color: #aaa;
            float: right;
            font-size: 1.5rem;
            cursor: pointer;
        }
        
        .login-form {
            margin-top: 1rem;
        }
        
        .form-group {
            margin-bottom: 1rem;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            color: #1a5276;
        }
        
        .form-group input {
            width: 100%;
            padding: 0.8rem;
            border: 1px solid #ddd;
            border-radius: 5px;
        }
        
        .login-btn {
            background-color: #1a5276;
            color: white;
            border: none;
            padding: 0.8rem;
            width: 100%;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        
        .login-btn:hover {
            background-color: #154360;
        }
        
        /* Hero Section */
        .hero {
            background: linear-gradient(rgba(0,0,0,0.5), rgba(0,0,0,0.5)), url('https://images.unsplash.com/photo-1506126613408-eca07ce68773?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80');
            background-size: cover;
            background-position: center;
            height: 60vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            color: white;
            padding: 0 1rem;
        }
        
        .hero h1 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }
        
        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
        }
        
        /* Main content - Grid */
        .container {
            display: grid;
            grid-template-columns: 1fr;
            gap: 2rem;
            padding: 3rem 2rem;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        .section-title {
            grid-column: 1 / -1;
            text-align: center;
            margin-bottom: 1rem;
            color: #1a5276;
        }
        
        .card {
            background-color: white;
            border-radius: 8px;
            padding: 2rem;
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
            transition: transform 0.3s;
        }
        
        .card:hover {
            transform: translateY(-5px);
        }
        
        .card h3 {
            margin-bottom: 1rem;
            color: #1a5276;
        }
        
        .card img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            border-radius: 5px;
            margin-bottom: 1rem;
        }
        
        /* Services Section */
        .services {
            background-color: #eaf2f8;
            padding: 3rem 0;
        }
        
        /* Contact Section */
        .contact-card {
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
        }
        
        .contact-icon {
            font-size: 2rem;
            color: #1a5276;
            margin-bottom: 1rem;
        }
        
        /* Footer - Flexbox */
        .footer {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            background-color: #1a5276;
            color: white;
            padding: 2rem;
            text-align: center;
        }
        
        .social-links {
            display: flex;
            gap: 1rem;
            margin-top: 1rem;
        }
        
        .social-links a {
            color: white;
            font-size: 1.5rem;
        }
        
        /* Button Styles */
        .btn {
            display: inline-block;
            background-color: #1a5276;
            color: white;
            padding: 0.8rem 1.5rem;
            border-radius: 5px;
            text-decoration: none;
            margin-top: 1rem;
            transition: background-color 0.3s;
        }
        
        .btn:hover {
            background-color: #154360;
        }
        
        /* Media Queries */
        
        /* Tablet */
        @media (min-width: 768px) {
            .container {
                grid-template-columns: repeat(2, 1fr);
            }
            
            .navbar {
                padding: 1rem 3rem;
            }
            
            .nav-links li {
                margin-left: 2rem;
            }
            
            .hero h1 {
                font-size: 3rem;
            }
        }
        
        /* Desktop */
        @media (min-width: 1024px) {
            .container {
                grid-template-columns: repeat(3, 1fr);
            }
            
            .about-section {
                grid-column: span 2;
            }
        }
        
        /* Mobile - Adjust navigation */
        @media (max-width: 600px) {
            .navbar {
                flex-direction: column;
                padding: 1rem;
            }
            
            .nav-links {
                margin-top: 1rem;
                flex-wrap: wrap;
                justify-content: center;
            }
            
            .nav-links li {
                margin: 0.5rem;
            }
            
            .hero {
                height: 50vh;
            }
            
            .hero h1 {
                font-size: 2rem;
            }
        }
    </style>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
</head>
<body>
    <nav class="navbar">
        <div class="logo">Safe Space Kenya</div>
        <ul class="nav-links">
            <li><a href="#home">Home</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#services">Services</a></li>
            <li><a href="#contact">Contact</a></li>
            <li><a href="#" id="loginBtn" class="employee-login">Employee Login</a></li>
        </ul>
    </nav>
    
    <!-- Login Modal -->
    <div id="loginModal" class="modal">
        <div class="modal-content">
            <span class="close-btn">&times;</span>
            <h2>Employee Login</h2>
            <p>Please enter your credentials to access the employee portal</p>
            
            <form class="login-form">
                <div class="form-group">
                    <label for="username">Username:</label>
                    <input type="text" id="username" placeholder="Enter your username" required>
                </div>
                
                <div class="form-group">
                    <label for="password">Password:</label>
                    <input type="password" id="password" placeholder="Enter your password" required>
                </div>
                
                <button type="submit" class="login-btn">Login</button>
                
                <div style="margin-top: 1rem; text-align: center;">
                    <a href="#" style="color: #1a5276;">Forgot password?</a>
                </div>
            </form>
            
            <div style="margin-top: 2rem; background-color: #f8f9fa; padding: 1rem; border-radius: 5px;">
                <h3>Login Instructions:</h3>
                <p>Use your assigned employee credentials. Contact admin if you need assistance.</p>
                <p><strong>Admin Contact:</strong> owinojerim269@gmail.com | 0758 943 430</p>
            </div>
        </div>
    </div>
    
    <section class="hero" id="home">
        <h1>Your Mental Health Matters</h1>
        <p>Professional counseling services in a safe, confidential environment. We're here to support you through life's challenges.</p>
        <a href="#contact" class="btn">Get Help Today</a>
    </section>
    
    <div class="container" id="about">
        <h2 class="section-title">About Safe Space Kenya</h2>
        <div class="card about-section">
            <h3>Our Mission</h3>
            <p>At Safe Space Kenya, we provide compassionate, professional counseling services to help individuals navigate life's challenges. Our team of qualified therapists creates a non-judgmental environment where you can explore your thoughts and feelings.</p>
            <p>We believe everyone deserves access to mental health support, and we're committed to making our services accessible to all Kenyans.</p>
        </div>
        <div class="card">
            <img src="https://images.unsplash.com/photo-1573497019940-1c28c88b4f3e?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Therapist office">
            <h3>Our Approach</h3>
            <p>We use evidence-based therapeutic approaches tailored to each client's unique needs, including CBT, psychodynamic therapy, and person-centered approaches.</p>
        </div>
    </div>
    
    <section class="services" id="services">
        <div class="container">
            <h2 class="section-title">Our Services</h2>
            <div class="card">
                <img src="https://images.unsplash.com/photo-1591348122449-8af5c1035180?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Individual therapy">
                <h3>Individual Counseling</h3>
                <p>One-on-one sessions to address personal challenges including anxiety, depression, trauma, and life transitions.</p>
            </div>
            <div class="card">
                <img src="https://images.unsplash.com/photo-1541178735493-479c1a27ed24?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Couples therapy">
                <h3>Couples Therapy</h3>
                <p>Helping partners improve communication, resolve conflicts, and strengthen their relationship.</p>
            </div>
            <div class="card">
                <img src="https://images.unsplash.com/photo-1529333166437-7750a6dd5a70?ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80" alt="Group therapy">
                <h3>Group Therapy</h3>
                <p>Supportive group sessions for shared experiences like grief, addiction recovery, or parenting challenges.</p>
            </div>
        </div>
    </section>
    
    <div class="container" id="contact">
        <h2 class="section-title">Contact Us</h2>
        <div class="card contact-card">
            <div class="contact-icon">
                <i class="fas fa-envelope"></i>
            </div>
            <h3>Email</h3>
            <p>owinojerim269@gmail.com</p>
            <a href="mailto:owinojerim269@gmail.com" class="btn">Send Email</a>
        </div>
        <div class="card contact-card">
            <div class="contact-icon">
                <i class="fas fa-phone"></i>
            </div>
            <h3>Phone</h3>
            <p>0758 943 430</p>
            <a href="tel:+254758943430" class="btn">Call Now</a>
        </div>
        <div class="card contact-card">
            <div class="contact-icon">
                <i class="fas fa-map-marker-alt"></i>
            </div>
            <h3>Location</h3>
            <p>Nairobi, Kenya</p>
            <p>By appointment only</p>
        </div>
    </div>
    
    <footer class="footer">
        <p>&copy; 2023 Safe Space Kenya. All rights reserved.</p>
        <p>Professional Counseling Services</p>
        <div class="social-links">
            <a href="#"><i class="fab fa-facebook"></i></a>
            <a href="#"><i class="fab fa-twitter"></i></a>
            <a href="#"><i class="fab fa-instagram"></i></a>
            <a href="#"><i class="fab fa-linkedin"></i></a>
        </div>
    </footer>
    
    <script>
        // Login Modal functionality
        const modal = document.getElementById("loginModal");
        const btn = document.getElementById("loginBtn");
        const span = document.getElementsByClassName("close-btn")[0];
        
        btn.onclick = function(e) {
            e.preventDefault();
            modal.style.display = "block";
        }
        
        span.onclick = function() {
            modal.style.display = "none";
        }
        
        window.onclick = function(event) {
            if (event.target == modal) {
                modal.style.display = "none";
            }
        }
        
        // Form submission (would connect to backend in real implementation)
        document.querySelector('.login-form').addEventListener('submit', function(e) {
            e.preventDefault();
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;
            
            // In a real implementation, this would connect to your authentication system
            alert('Login functionality would connect to backend system\n\nUsername: ' + username + '\nPassword: ' + password);
            
            // For demo purposes, we'll just close the modal
            modal.style.display = "none";
        });
    </script>
</body>
</html>


