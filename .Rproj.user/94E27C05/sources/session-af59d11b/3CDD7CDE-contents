document.addEventListener('DOMContentLoaded', function() {
  const carousel = document.querySelector('.carousel');
  const slides = carousel.querySelectorAll('.slide');
  const navigation = document.querySelector('.navigation');
  const navigationButtons = navigation.querySelectorAll('button');
  const thumbnailNavigation = document.querySelector('.thumbnail-navigation');
  const thumbnailSlides = thumbnailNavigation.querySelectorAll('.thumbnail-slide');
  const previousButton = document.querySelector('.previous-button');
  const nextButton = document.querySelector('.next-button');

  // Add event listeners to navigation buttons
  navigationButtons.forEach((button, index) => {
    button.addEventListener('click', () => {
      // Remove active class from all buttons
      navigationButtons.forEach((btn) => btn.classList.remove('active'));

      // Add active class to the clicked button
      button.classList.add('active');

      // Scroll to the corresponding slide
      slides[index].scrollIntoView({ behavior: 'smooth' });
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
    });
  });

  // Scroll event listener to update active button and thumbnail slide
  carousel.addEventListener('scroll', () => {
    const activeSlideIndex = Math.round(carousel.scrollLeft / carousel.offsetWidth);
    updateActiveSlide(activeSlideIndex);
  });

  // Previous button click event listener
  previousButton.addEventListener('click', () => {
    const activeSlideIndex = Array.from(slides).findIndex((slide) => slide.classList.contains('active'));

    const previousSlideIndex = activeSlideIndex - 1;
    if (previousSlideIndex >= 0) {
      slides[previousSlideIndex].scrollIntoView({ behavior: 'smooth', inline: 'center' });
    }
  });

  // Next button click event listener
  nextButton.addEventListener('click', () => {
    const activeSlideIndex = Array.from(slides).findIndex((slide) => slide.classList.contains('active'));

    const nextSlideIndex = activeSlideIndex + 1;
    if (nextSlideIndex < slides.length) {
      slides[nextSlideIndex].scrollIntoView({ behavior: 'smooth', inline: 'center' });
    }
  });

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
