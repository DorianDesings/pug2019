Curso de PUG 2019

Sintaxis:
    La sintaxis de pug nos permite escribir HTML de una forma más sencilla y libre de etiquetas.

    h1 hola mundo 
    
    es quivalente a
    
    <h1> hola mundo </h1>

    Para anidar elementos basta con añadir una indentación al elemento hijo

    ul
      li Item 1

    es equivalente a

    <ul>
      <li>Item 1</li>
    </ul>

    Los atributos se colocan entre paréntesis
      a(href="#") Soy un enlace
    es equivalente a 
      <a href="#">Soy un enlace</a>

    Si hubiera más de un atributo se pueden separar por comas o por espacios
      img(src="foto.jpg", alt="una foto")
      img(src="foto.jpg" alt="una foto")

      es equivalente a 

      <img src="foto.jpg" alt="una foto"/>
      <img src="foto.jpg" alt="una foto"/>

    Los ids y las clases se aplican con # y . respectívamente
      p#text párrafo con ID
      p.text párrafo con clase
      p#text.text párrafo con ID y clase

      es equivalente a 

      <p id="text">párrafo con ID</p>
      <p class="text">párrafo con clase</p>
      <p class="text" id="text">párrafo con ID y clase</p>

    Para intercalar hijos dentro de elementos se utiliza el |

      p Lorem ipsum dolor sit amet consectetur adipisicing elit. Vitae enim quam debitis nisi aut est quo accusantium quasi
        a(href="#") incidunt
        |vel molestiae facere culpa eos obcaecati cumque eum cupiditate rem blanditiis. Lorem ipsum dolor sit amet consectetur adipisicing elit. Magnam excepturi dignissimos voluptate, quidem soluta rerum veniam totam laborum maxime at fugit

    Si no queremos hacer muchos saltos en elementos que ocupan poco tenemos la opción de utilizar :

      ul.menu
        li.menu__item: a(href="#").menu__link Item 1

      es equivalente a 

      <ul class="menu">
        <li class="menu__item">
          <a class="menu__link" href="#">Item 1</a>
        </li>
      </ul>

