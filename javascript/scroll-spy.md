```html
  <!DOCTYPE html>

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Scroll Spy</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            font-family: 'Arial', sans-serif;
        }
  
        section {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
        }


        section:nth-child(even) {
            background-color: #f0f0f0;
        }

        .active {
           color:red;
        }


        header {
           position:fixed;
           top:0;
           left:0;
           width:100%;
           z-index:9999;
        }

    </style>
</head>

<!-- ... (previous HTML code) ... -->

  
<body>
  <header>
      <nav>
          <ul>
              <li><a href="#section1">Section 1</a></li>
              <li><a href="#section2">Section 2</a></li>
              <li>
                  <a href="#section3">Section 3</a>
                  <ul>
                      <li><a href="#section3-1">Section 3.1</a></li>
                      <li><a href="#section3-2">Section 3.2</a></li>
                  </ul>
              </li>
              <li><a href="#section4">Section 4</a></li>
          </ul>
      </nav>
  </header>



  <section id="section1">
      <h2>Section 1</h2>
  </section>

  
  <section id="section2">
      <h2>Section 2</h2>
  </section>


  <section id="section3">
      <h2>Section 3</h2>
       <section id="section3-1">
        <div >
          <h3>Section 3.1</h3>
      </div></section>
      <div id="section3-2">
          <h3>Section 3.2</h3>
      </div>
  </section>

  

  <section id="section4">
      <h2>Section 4</h2>
  </section>


  <script src="scrollspy.js"></script>
</body>
</html>
```




```javascript
  document.addEventListener('DOMContentLoaded', function () {

  const sections = document.querySelectorAll('section');
  const navLinks = document.querySelectorAll('nav ul li a');



  window.addEventListener('scroll', function () {
      let current = '';


      sections.forEach(section => {
          const sectionTop = section.offsetTop;
          const sectionHeight = section.clientHeight;
          if (pageYOffset >= sectionTop - sectionHeight / 3) {
              current = section.getAttribute('id');
          }

      });


      navLinks.forEach(link => {
          link.classList.remove('active');
          if (link.getAttribute('href').includes(current)) {
              link.classList.add('active');
          }
      });
  });

});
```

#javascript #scroll-spy
