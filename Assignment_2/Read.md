<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Space Exploration Slideshow</title>
  <style>
    /* Reset and base styles */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
      background-color: #0a0a14;
      color: #fff;
      height: 100vh;
      overflow: hidden;
    }

    /* Main container */
    .slideshow-container {
      position: relative;
      width: 100%;
      height: 100vh;
      overflow: hidden;
    }

    /* Slide styles */
    .slide {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      opacity: 0;
      transition: opacity 0.5s ease-in-out;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
    }

    .slide.active {
      opacity: 1;
      z-index: 10;
    }

    /* Image container */
    .slide-image {
      width: 100%;
      height: 80%;
      background-position: center;
      background-size: contain;
      background-repeat: no-repeat;
    }

    /* Content container */
    .slide-content {
      width: 100%;
      max-width: 900px;
      padding: 1rem 2rem 5rem;
      position: relative;
      background-color: #0a0a14;
    }

    .slide-title {
      font-size: 1.8rem;
      font-weight: bold;
      margin-bottom: 0.75rem;
      color: white;
    }

    .slide-description {
      font-size: 1.1rem;
      line-height: 1.5;
      color: #e0e0e0;
    }

    /* Navigation buttons */
    .nav-button {
      position: absolute;
      top: 33%;
      transform: translateY(-50%);
      z-index: 20;
      width: 40px;
      height: 40px;
      border: none;
      border-radius: 50%;
      background-color: rgba(0, 0, 0, 0.7);
      color: white;
      font-size: 1.2rem;
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;
      transition: background-color 0.3s;
    }

    .nav-button:hover {
      background-color: rgba(255, 255, 255, 0.3);
    }

    .prev-button {
      left: 10px;
    }

    .next-button {
      right: 10px;
    }

    /* Next button within slide */
    .slide-next-button {
      position: absolute;
      bottom: 20px;
      right: 20px;
      padding: 8px 30px;
      background-color: white;
      color: black;
      border: none;
      border-radius: 50px;
      font-weight: 600;
      cursor: pointer;
      transition: background-color 0.3s;
      box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    }

    .slide-next-button:hover {
      background-color: #e0e0e0;
    }

    /* Progress indicator */
    .progress-bar {
      position: absolute;
      bottom: 10px;
      left: 50%;
      transform: translateX(-50%);
      z-index: 20;
      display: flex;
      gap: 12px;
    }

    .progress-dot {
      width: 12px;
      height: 12px;
      border-radius: 50%;
      background-color: rgba(255, 255, 255, 0.3);
      cursor: pointer;
      transition: transform 0.3s, background-color 0.3s;
    }

    .progress-dot.active {
      transform: scale(1.25);
      background-color: white;
    }

    /* Responsive adjustments */
    @media (max-width: 768px) {
      .slide-title {
        font-size: 1.5rem;
      }
      
      .slide-description {
        font-size: 1rem;
      }
      
      .slide-content {
        padding: 1rem 1.5rem 4rem;
      }
    }
  </style>
</head>
<body>
  <div class="slideshow-container" id="slideshow">
    <!-- Slide 1 -->
    <div class="slide" id="slide1">
      <div class="slide-image" style="background-image: url('assets/wt%20ass%202%20page%201.jpg');"></div>
      <div class="slide-content">
        <h2 class="slide-title">Space Exploration Simulation</h2>
        <p class="slide-description">Experience space missions and explore celestial bodies in a virtual environment</p>
        <button class="slide-next-button" onclick="goToSlide(1)">next</button>
      </div>
    </div>

    <!-- Slide 2 -->
    <div class="slide" id="slide2">
      <div class="slide-image" style="background-image: url('assets/page%202.jpg');"></div>
      <div class="slide-content">
        <h2 class="slide-title">Aditya L1 - India's Solar Mission</h2>
        <p class="slide-description">Aditya L1, India's first solar mission, was launched on September 2, 2023. It reached the Sun-Earth Lagrange point 1 on January 6, 2024. The mission's goal is to study the Sun's atmosphere and space weather. In early 2025, it will collaborate with the European Space Agency's Proba-3 mission for joint solar observations. This mission represents a significant step in understanding our closest star.</p>
        <button class="slide-next-button" onclick="goToSlide(2)">next</button>
      </div>
    </div>

    <!-- Slide 3 -->
    <div class="slide" id="slide3">
      <div class="slide-image" style="background-image: url('assets/page%203.jpg');"></div>
      <div class="slide-content">
        <h2 class="slide-title">Apollo 11 - First Humans on the Moon</h2>
        <p class="slide-description">The Apollo 11 mission, launched by NASA in July 1969, was the first successful manned mission to land on the Moon. Commander Neil Armstrong and Lunar Module Pilot Buzz Aldrin became the first humans to walk on the lunar surface, while Command Module Pilot Michael Collins orbited above. This historic event marked a significant achievement in space exploration.</p>
        <button class="slide-next-button" onclick="goToSlide(3)">next</button>
      </div>
    </div>

    <!-- Slide 4 -->
    <div class="slide" id="slide4">
      <div class="slide-image" style="background-image: url('assets/page%204.jpg');"></div>
      <div class="slide-content">
        <h2 class="slide-title">Mangalyaan - India's Mars Orbiter Mission</h2>
        <p class="slide-description">Mangalyaan, or the Mars Orbiter Mission, was India's first interplanetary mission. It launched in 2013 and orbited Mars from 2014 until April 2022, when communication was lost. It provided valuable data on Mars' surface and atmosphere.</p>
        <button class="slide-next-button" onclick="goToSlide(4)">next</button>
      </div>
    </div>

    <!-- Slide 5 -->
    <div class="slide" id="slide5">
      <div class="slide-image" style="background-image: url('assets/page%205.jpg');"></div>
      <div class="slide-content">
        <h2 class="slide-title">Luna 2 - First Spacecraft to Reach the Moon</h2>
        <p class="slide-description">Luna 2, launched by the Soviet Union on September 12, 1959, was the first spacecraft to reach the Moon. It impacted the lunar surface on September 14, 1959, between Mare Imbrium and Mare Serenitatis. This mission marked a significant milestone in space exploration.</p>
        <button class="slide-next-button" onclick="goToSlide(5)">next</button>
      </div>
    </div>

    <!-- Slide 6 -->
    <div class="slide" id="slide6">
      <div class="slide-image" style="background-image: url('assets/page%206.jpg');"></div>
      <div class="slide-content">
        <h2 class="slide-title">International Space Station (ISS)</h2>
        <p class="slide-description">The International Space Station (ISS) is a large spacecraft orbiting Earth, serving as a home for astronauts and a science lab. It was launched in 1998 and is a joint project involving NASA, Roscosmos, JAXA, ESA, and CSA. The ISS orbits Earth every 90 minutes and provides a unique environment for scientific research in microgravity. It has been continuously inhabited since November 2000 by rotating crews of astronauts.</p>
        <button class="slide-next-button" onclick="goToSlide(6)">next</button>
      </div>
    </div>

    <!-- Slide 7 -->
    <div class="slide" id="slide7">
      <div class="slide-image" style="background-image: url('assets/page%207.jpg');"></div>
      <div class="slide-content">
        <h2 class="slide-title">Celestial Bodies</h2>
        <p class="slide-description">Celestial bodies are natural objects in space, such as stars, planets, moons, asteroids, and comets. They come in various forms and sizes and are held together by gravity. These objects are fundamental components of the universe.</p>
        <button class="slide-next-button" onclick="goToSlide(7)">next</button>
      </div>
    </div>

    <!-- Slide 8 -->
    <div class="slide" id="slide8">
      <div class="slide-image" style="background-image: url('assets/page%208.jpg');"></div>
      <div class="slide-content">
        <h2 class="slide-title">Types of Celestial Bodies</h2>
        <p class="slide-description">Celestial bodies come in various forms, each playing a crucial role in the universe. Stars are massive, luminous spheres of plasma that generate heat and light, with the Sun being the closest star to Earth. Planets are large objects that orbit stars, such as Earth and Jupiter, and can be categorized as rocky or gas giants. Moons are natural satellites that revolve around planets, like our own Moon, influencing tides and planetary stability. Additionally, smaller celestial bodies like asteroids and comets, composed of rock, metal, and ice, travel through space, sometimes entering planetary atmospheres as meteors.</p>
      </div>
    </div>

    <!-- Navigation Buttons -->
    <button class="nav-button prev-button" onclick="previousSlide()">&#10094;</button>
    <button class="nav-button next-button" onclick="nextSlide()">&#10095;</button>

    <!-- Progress Indicator -->
    <div class="progress-bar" id="progress-bar"></div>
  </div>

  <script>
    // JavaScript for slideshow functionality
    let currentSlide = 0;
    const slides = document.querySelectorAll('.slide');
    const totalSlides = slides.length;

    // Initialize slideshow
    function initSlideshow() {
      // Set the first slide as active
      slides[0].classList.add('active');
      
      // Create progress dots
      const progressBar = document.getElementById('progress-bar');
      for (let i = 0; i < totalSlides; i++) {
        const dot = document.createElement('div');
        dot.classList.add('progress-dot');
        if (i === 0) dot.classList.add('active');
        dot.addEventListener('click', () => goToSlide(i));
        progressBar.appendChild(dot);
      }

      // Add keyboard navigation
      document.addEventListener('keydown', (e) => {
        if (e.key === 'ArrowLeft') {
          previousSlide();
        } else if (e.key === 'ArrowRight') {
          nextSlide();
        }
      });
    }

    // Go to specific slide
    function goToSlide(index) {
      if (index >= 0 && index < totalSlides) {
        slides[currentSlide].classList.remove('active');
        currentSlide = index;
        slides[currentSlide].classList.add('active');
        updateProgressDots();
        updateNavigationButtons();
      }
    }

    // Go to previous slide
    function previousSlide() {
      goToSlide(currentSlide - 1);
    }

    // Go to next slide
    function nextSlide() {
      goToSlide(currentSlide + 1);
    }

    // Update progress dots
    function updateProgressDots() {
      const dots = document.querySelectorAll('.progress-dot');
      dots.forEach((dot, i) => {
        if (i === currentSlide) {
          dot.classList.add('active');
        } else {
          dot.classList.remove('active');
        }
      });
    }

    // Update navigation buttons visibility
    function updateNavigationButtons() {
      const prevButton = document.querySelector('.prev-button');
      const nextButton = document.querySelector('.next-button');
      
      if (currentSlide === 0) {
        prevButton.style.visibility = 'hidden';
      } else {
        prevButton.style.visibility = 'visible';
      }
      
      if (currentSlide === totalSlides - 1) {
        nextButton.style.visibility = 'hidden';
      } else {
        nextButton.style.visibility = 'visible';
      }
    }

    // Initialize the slideshow on page load
    window.onload = initSlideshow;
  </script>
</body>
</html>

