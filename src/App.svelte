<script>
  import { games } from "./gameList";
  import GameCard from "./GameCard.svelte";
</script>

<style>
  .landing-header {
    display: grid;
    /* background: black; */
    background-image: linear-gradient(
        to bottom,
        rgba(28, 28, 29, 0.911),
        rgba(5, 5, 5, 0.938)
      ),
      url("../images/bbgif.gif");
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    min-height: 70vh;
    font-family: "Press Start 2P", cursive;
    color: white;
    place-items: center center;
  }

  h1 {
    font-size: 3vw;
  }

  .game-gallery {
    display: grid;
    grid-gap: 40px;
    max-width: 1000px;
    margin-left: auto;
    margin-right: auto;
    padding-top: 100px;
    grid-template-columns: 1fr 1fr 1fr;
    place-items: center;
    padding-bottom: 100px;
  }

  .page-footer {
    display: grid;
    background: rgba(128, 128, 128, 0.7);
    padding: 40px;
    min-height: 20vh;
    font-size: 22px;
    font-family: "Ubuntu Mono", monospace;
    place-items: center center;
    text-align: center;
  }

  .page-footer img {
    height: 22px;
    width: auto;
  }

  .page-footer a {
    color: black;
    text-decoration: none;
    transition: ease-in-out 0.2s;
  }

  .page-footer a:hover {
    color: white;
  }

  .site-info {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-gap: 40px;
    max-width: 1000px;
    margin-left: auto;
    margin-right: auto;
    padding-top: 100px;
    font-family: "Ubuntu Mono", monospace;
    line-height: 1.2em;
  }

  .site-info a {
    color: rgb(66, 4, 71);
    text-decoration: none;
    border-bottom: solid 1px transparent;
    padding-bottom: 1px;
    transition: ease-in-out 0.2s;
  }

  .site-info a:hover {
    border-bottom: solid 2px rgb(66, 4, 71);
  }

  .site-info h3 {
    font-family: "Press Start 2P", cursive;
    grid-column: 1 / -1;
  }

  .stack {
    display: grid;
    place-items: center;
    grid-gap: 10px;
    grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
  }

  .stack img {
    width: 10vw;
    height: auto;
    border-radius: 6px;
  }

  .progress {
    display: grid;
    place-items: center;
    grid-gap: 10px;
    grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
  }

  .progress img {
    width: 100%;
    height: auto;
    border-radius: 6px;
  }

  @media (max-width: 800px) {
    .game-gallery {
      grid-template-columns: 1fr;
      margin-left: 10vw;
      margin-right: 10vw;
    }

    .site-info {
      grid-template-columns: 1fr;
      margin-left: 10vw;
      margin-right: 10vw;
    }
  }
</style>

<div class="landing-header">
  <h1>ALTAMONT ARCADE</h1>
</div>
<div class="site-info">
  <h3>Welcome to our online arcade!</h3>
  <p>
    If you've come to play some games, or learn a bit about
    <a href="https://www.altamontschool.org/" target="_blank">our CS program</a>,
    you're in the right place!
    <br /><br />
    All the games listed in our gallery below were built by middle school
    computer science students. Students used the
    <a href="https://arcade.makecode.com/" target="_blank">Microsoft MakeCode
      Arcade</a>
    and developed the games exclusively using JavaScript. Additionally. to
    illustrate their knowledge of working with open source software, they added
    their games to this site using pull requets on Github.
    <br /><br />
    All of this site's code is available via Github and can be viewed or edited
    by anyone. We're also building an arcade for use after COVID-19. Scroll down
    and get to playing!
  </p>
  <div class="stack">
    <img src="./images/makeCode.jpg" alt="" />
    <img src="./images/JavaScript-logo.png" alt="" />
    <img src="./images/githubLogo.png" alt="" />
  </div>
</div>
<div class="game-gallery">
  {#each games as { description, title, image, author, term, link, genre }, i}
    <GameCard {title} {description} {image} {author} {term} {link} {genre} />
  {/each}
</div>
<!-- <div class="site-info" style="margin-top: 20px; margin-bottom: 40px;">
  <h3>We're also building an arcade!</h3>
  <p>
    There will be more info here soon, but take a look at our progress pics...
  </p>
  <div class="progress">
    <div class="stack"><img src="./images/sketch.png" alt="" /></div>
  </div>
</div> -->
<div class="page-footer">
  <div class="footer-text">
    <p>
      <a href="https://www.dominguezdev.com" target="_blank">Built</a>
      with
      <a href="https://svelte.dev/" target="_blank"><img
          src="./images/1200px-Svelte_Logo.svg.png"
          alt="" /></a>
      |
      <a
        href="https://github.com/robertjdominguez/altamont-arcade"
        target="_blank"><i class="fas fa-code" /></a>
      on
      <i class="fab fa-github" />
    </p>
    <p>&copy;{new Date().getFullYear()}</p>
  </div>
</div>
