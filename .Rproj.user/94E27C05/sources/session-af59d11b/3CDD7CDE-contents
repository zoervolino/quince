document.addEventListener('DOMContentLoaded', function() {
  const carousel = document.querySelector('.carousel');
  const slides = carousel.querySelectorAll('.slide');
  const navigation = document.querySelector('.navigation');
  const navigationButtons = navigation.querySelectorAll('button');
  const thumbnailNavigation = document.querySelector('.thumbnail-navigation');
  const thumbnailSlides = thumbnailNavigation.querySelectorAll('.thumbnail-slide');
  const previousButton = document.querySelector('.previous-button');
  const nextButton = document.querySelector('.next-button');
  let currentIndex = 0;
  let autoplayInterval;

  // Add event listeners to navigation buttons
  navigationButtons.forEach((button, index) => {
    button.addEventListener('click', () => {
      // Remove active class from all buttons
      navigationButtons.forEach((btn) => btn.classList.remove('active'));

      // Add active class to the clicked button
      button.classList.add('active');

      // Scroll to the corresponding slide
      slides[index].scrollIntoView({ behavior: 'smooth' });

      // Update the current index
      currentIndex = index;
    });
  });

  // Add event listeners to thumbnail slides
  thumbnailSlides.forEach((thumbnailSlide, index) => {
    thumbnailSlide.addEventListener('click', () => {
      // Remove active class from all thumbnail slides
      thumbnailSlides.forEach((slide) => slide.classList.remove('active'));

      // Add active class to the clicked thumbnail slide
      thumbnailSlide.classList.add('active');

      // Scroll to the corresponding slide
      slides[index].scrollIntoView({ behavior: 'smooth' });

      // Update the current index
      currentIndex = index;
    });
  });

  // Scroll event listener to update active button and thumbnail slide
  carousel.addEventListener('scroll', () => {
    const activeSlideIndex = Math.round(carousel.scrollLeft / carousel.offsetWidth);
    updateActiveSlide(activeSlideIndex);
  });

  // Previous button click event listener
  previousButton.addEventListener('click', () => {
    changeSlide('previous');
    restartAutoplay();
  });

  // Next button click event listener
  nextButton.addEventListener('click', () => {
    changeSlide('next');
    restartAutoplay();
  });

  // Start autoplay
  startAutoplay();

  function startAutoplay() {
    autoplayInterval = setInterval(() => {
      changeSlide('next');
    }, 3000);
  }

  function stopAutoplay() {
    clearInterval(autoplayInterval);
  }

  function restartAutoplay() {
    stopAutoplay();
    startAutoplay();
  }

  function changeSlide(direction) {
    const activeSlideIndex = Array.from(slides).findIndex((slide) => slide.classList.contains('active'));

    let newSlideIndex;
    if (direction === 'previous') {
      newSlideIndex = activeSlideIndex - 1;
      if (newSlideIndex < 0) {
        newSlideIndex = slides.length - 1;
      }
    } else if (direction === 'next') {
      newSlideIndex = activeSlideIndex + 1;
      if (newSlideIndex >= slides.length) {
        newSlideIndex = 0;
      }
    }

    // Scroll to the new slide
    slides[newSlideIndex].scrollIntoView({ behavior: 'smooth', inline: 'center' });

    // Update the current index
    currentIndex = newSlideIndex;
  }

  function updateActiveSlide(activeSlideIndex) {
    navigationButtons.forEach((button, index) => {
      if (index === activeSlideIndex) {
        button.classList.add('active');
      } else {
        button.classList.remove('active');
      }
    });

    thumbnailSlides.forEach((thumbnailSlide, index) => {
      if (index === activeSlideIndex) {
        thumbnailSlide.classList.add('active');
      } else {
        thumbnailSlide.classList.remove('active');
      }
    });
  }
});
