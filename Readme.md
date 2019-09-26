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

  Utilizar CSS en pug
    Importar hoja de estilos-> link(rel="stylesheet" href="style.css")
    CSS integrado: Es muy importante el punto después de style SIN ESPACIO
      style.
        body{
          background-color:red
        }
    CSS en línea
      header(style={"background-color": "blue", "margin-top":"30px"})
      
  Importar hoja de JavaScript
    script(src="scripts.js")
  Utilizar JavaScript embebido. Al igual que en CSS es muy importante el punto SIN ESPACIOS
    script.
      const alert = () =>{
        alert('Hola Mundo')
      }
      
  Variables JavaScript
    -const name = "Dorian"

    p= `Hola ${name}` Esta es la forma recomendada

    p Hola #{name} Creo que ya no es válida

  Arrays
      -const numbers = [1,2,3,4,5]
      ul
        li= numbers[0]
        li= numbers[1]
        li= numbers[2]
        li= numbers[3]
        li= numbers[4]

  Objetos
  Es muy importante poner el guión y después un salto de línea e indentar, si no NO FUNCIONA
  -
    const person = {
      name: "Dorian",
      surname: "Desings",
      age: 30
    }

  Condicionales
    Los condicionales en pug funcionan igual que en JavaScript pero sin paréntesis ni llaves
      if username
        p Bienvenido usuario
      else
        p Registrese para continuar

      if username
        p Bienvenido usuario
      else if username == null
        p username no existe
      else 
        p Registrese para continuar

    El operador ternario funciona igual que en JavaScript
      p(class= username ? 'registered' : 'unregistered')

    Tenemos un equivalente al operador de negación pero que apenas se utiliza
      unless username

      equivale a

      if !username

  Bucles
    Existen dos bucles en pug
      each:
        Sirve para recorrer elementos
          -const names = ['dorian', 'laura', 'marta', 'carlos']
           each name in names
        Tenemos la opción de añadir un segundo valor que sería el index en los arrays y el key en objetos
          each name, index in names
          each value, key in object

        También podemos establecer un "caso contrario" por si no hubiera elementos que recorrer
        -const names = []
        each name in names.length ? names : ['No names']
          p= name

        each name in names
          p= name
        else
          p= 'no names'

    while
      - let n = 0;
        ul
          while n < 4
          li= n++

//CORRECCIÓN DEL PACKAJE.JSON
  Debeis realizar 2 instalaciones:
  npm i @babel/register
  npm i @babel/core
  Eliminad el archivo .babelrc


  
       


