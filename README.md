Bankist - website
=======================================

HTML, CSS, JavaScript

Main goal -> animations and lazy loading practice with intersection observer

* * *
### [Demo](https://cold-world.github.io/bankist-website/)

![Alt Text](https://i.ibb.co/d4nkpKR/Screenshot-2023-03-29-101920.jpg)

* * *



### A piece of code

```// Lazy images
const loadImg = (entries, observer) => {
  const [entry] = entries;
  
  if (!entry.isIntersecting) return;
  
  entry.target.src = entry.target.dataset.src;
  entry.target.addEventListener('load', () => {
    entry.target.classList.remove('lazy-img');
  });
  observer.unobserve(entry.target);
};

const imgTargets = document.querySelectorAll('img[data-src]');
const imgObserver = new IntersectionObserver(loadImg, {
  root: null,
  threshold: 0,
});

imgTargets.forEach((img) => imgObserver.observe(img));
```

### Download & Installation

```shell 
$ git clone https://github.com/cold-world/bankist-website.git
```
