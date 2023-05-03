# Angular-Improve-Performance
Function debouncing

The Unresponsive Site
// Expensive calculations on scroll event
window.addEventListener("scroll", () => {
  expensiveCalculation();
});


// Debounce function to imporove performance
function debounce(func, wait) {
  let timeout;
  return function () {
    clearTimeout(timeout);
    timeout = setTimeout(() => func.apply(this, arguments), wait);
  };
}

// Debounced scroll event
window.addEventListener("scroll", debounce(() => {
  expensiveCalculation();
}, 250));
