document.addEventListener('DOMContentLoaded', function() {
  const carousel = document.querySelector('.carousel');
  const slides = carousel.querySelectorAll('.slide');
  const navigation = document.querySelector('.navigation');
  const navigationButtons = navigation.querySelectorAll('button');
  const thumbnailNavigation = document.querySelector('.thumbnail-navigation');
  const thumbnailSlides = thumbnailNavigation.querySelectorAll('.thumbnail-slide');
  const previousButton = document.querySelector('.previous-button');
  const nextButton = document.querySelector('.next-button');

  let currentSlide = 0;
  let autoplayInterval;

  // Function to switch to the next slide
  function nextSlide() {
    currentSlide = (currentSlide + 1) % slides.length;
    slides[currentSlide].scrollIntoView({ behavior: 'smooth', inline: 'center' });
  }

  // Start autoplay when the DOM is loaded
  autoplayInterval = setInterval(nextSlide, 5000); // Change 5000 to adjust the time interval between slides (in milliseconds)

  // Pause autoplay on user interaction (clicking navigation buttons or thumbnail slides)
  function pauseAutoplay() {
    clearInterval(autoplayInterval);
  }

  // Add event listeners to navigation buttons
  navigationButtons.forEach((button, index) => {
    button.addEventListener('click', () => {
      pauseAutoplay();
      // Rest of your existing code
      // ...
    });
  });

  // Add event listeners to thumbnail slides
  thumbnailSlides.forEach((thumbnailSlide, index) => {
    thumbnailSlide.addEventListener('click', () => {
      pauseAutoplay();
      // Rest of your existing code
      // ...
    });
  });

  // Rest of your existing code
  // ...

  function updateActiveSlide(activeSlideIndex) {
    // Rest of your existing code
    // ...
  }
});
