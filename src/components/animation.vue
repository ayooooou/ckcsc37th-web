<script>
function isElementInViewport(el) {
  const rect = el.getBoundingClientRect();
  return rect.bottom < 0 || rect.top > window.innerHeight;
}
function addClassToVisibleElements() {
  var aosElements = document.querySelectorAll(".aos");
  aosElements.forEach(function (aosElement) {
    if (!isElementInViewport(aosElement)) aosElement.classList.add("ed");
    // else aosElement.classList.remove("ed"); 移開後要不要再隱藏
  });
  var bounceElements = document.querySelectorAll(".bounce");
  bounceElements.forEach(function (bounceElement) {
    if (!isElementInViewport(bounceElement)) bounceElement.classList.add("ed");
    // else bounceElement.classList.remove("ed"); 
  });
}
document.addEventListener("scroll", addClassToVisibleElements);
addClassToVisibleElements();
</script>

<style>

@keyframes fadeIn{
            0% {
                opacity: 0.1;
                transform: translateY(-30px);
            }
            100% {
                opacity: 1;
                transform: translateY(0);
            }
        }

@keyframes bounce-in {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(1.25);
  }
  100% {
    transform: scale(1);
    opacity: 1;
  }
}

.aos {
  opacity: 0;
  transition: fadeIn 0.3s;
}

.aos.ed {
  animation-name: fadeIn;
  animation-duration: 0.5s;
  animation-delay: 0.5s;
  animation-fill-mode: forwards;
}

.bounce{
  opacity: 0;
  transition: bounce-in 0.3s;
}

.bounce.ed{
  animation-name: bounce-in;
  animation-duration: 0.5s;
  animation-delay: 0.5s;
  animation-fill-mode: forwards;
}
</style>
