# Final Project and Deployment

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Website</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: Arial, sans-serif;
        }

        header {
            background-color: #333;
            color: white;
            padding: 10px;
        }

        nav ul {
            display: flex;
            list-style: none;
            justify-content: center;
        }

        nav ul li {
            margin: 0 20px;
        }

        nav ul li a {
            color: white;
            text-decoration: none;
            font-size: 18px;
        }

        main {
            padding: 20px;
        }

        .banner img {
            width: 100%;
            height: auto;
        }

        .content {
            text-align: center;
            margin-top: 20px;
        }

        .slider-container {
            display: flex;
            justify-content: center;
            gap: 20px;
        }

        .slider-container img {
            width: 100px;
            height: 100px;
        }

        footer {
            text-align: center;
            margin-top: 20px;
        }

        /* Responsive design */
        @media (max-width: 768px) {
            nav ul {
                flex-direction: column;
            }

            .slider-container {
                flex-direction: column;
            }

            .slider-container img {
                width: 80%;
                height: auto;
            }
        }

    </style>
</head>
<body>

    <header>
        <nav>
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <main id="home">
        <section class="banner">
            <img src="https://via.placeholder.com/1200x400" alt="Banner Image">
        </section>

        <section class="content">
            <h1>Welcome to My Website</h1>
            <p>This is the home page of my amazing website.</p>
        </section>

        <section class="slider">
            <h2>Image Slider</h2>
            <div class="slider-container">
                <img class="slide" src="https://via.placeholder.com/300x150" alt="Slide 1">
                <img class="slide" src="https://via.placeholder.com/300x150" alt="Slide 2">
                <img class="slide" src="https://via.placeholder.com/300x150" alt="Slide 3">
            </div>
        </section>
    </main>

    <main id="about">
        <section class="content">
            <h1>About Us</h1>
            <p>We are a company dedicated to providing the best services.</p>
        </section>
    </main>

    <main id="contact">
        <section class="content">
            <h1>Contact Us</h1>
            <form id="contactForm">
                <label for="name">Name:</label>
                <input type="text" id="name" name="name" required placeholder="Enter your name">

                <label for="email">Email:</label>
                <input type="email" id="email" name="email" required placeholder="Enter your email">

                <label for="message">Message:</label>
                <textarea id="message" name="message" required placeholder="Your message"></textarea>

                <button type="submit">Send Message</button>
            </form>
        </section>
    </main>

    <footer>
        <p>&copy; 2025 My Website</p>
    </footer>

    <script>
        // Image Slider (basic example)
        let currentSlide = 0;
        const slides = document.querySelectorAll('.slide');

        function showSlide() {
            slides.forEach((slide, index) => {
                slide.style.display = (index === currentSlide) ? 'block' : 'none';
            });
        }

        function nextSlide() {
            currentSlide = (currentSlide + 1) % slides.length;
            showSlide();
        }

        setInterval(nextSlide, 3000); // Change slide every 3 seconds

        // Contact Form Validation
        const contactForm = document.getElementById('contactForm');

        contactForm.addEventListener('submit', function(e) {
            e.preventDefault();

            const name = document.getElementById('name').value;
            const email = document.getElementById('email').value;
            const message = document.getElementById('message').value;

            if (name && email && message) {
                alert('Message sent successfully!');
            } else {
                alert('Please fill in all fields.');
            }
        });
    </script>

</body>
</html>

