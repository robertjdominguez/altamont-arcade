<script>
  export let title;
  export let description;
  export let image;
  export let author;
  export let term;
  export let link;
  export let genre;
</script>

<style>
  .card {
    display: grid;
    align-self: start;
    border-radius: 8px;
    width: 100%;
    min-height: 300px;
    padding: 20px;
    margin: 0;
  }

  .card h2 {
    font-family: "Press Start 2P", cursive;
    font-size: 18px;
  }

  .card h3 {
    font-family: "Press Start 2P", cursive;
    font-size: 10px;
  }

  .card p {
    font-family: "Ubuntu Mono", monospace;
  }

  .card img {
    width: 100%;
    max-height: auto;
  }

  .card a {
    text-decoration: none;
    color: black;
    font-family: "Ubuntu Mono", monospace;
    transition: ease-in-out 0.2s;
    margin-top: 10px;
    padding: 8px 15px;
    justify-self: start;
    border: solid 1px black;
  }

  .card a:hover {
    transform: translateY(-5px);
    background: black;
    color: white;
  }

  .genre {
    font-family: "Press Start 2P", cursive;
    font-size: 14px;
    padding: 4px 8px;
    margin-top: 8px;
    margin-bottom: 0;
    background: rgba(30, 128, 0, 0.521);
    place-self: start;
    border-radius: 6px;
  }
</style>

<div class="card">
  <h2>{title}</h2>
  <img src={image} alt="Ballard's Birds" />
  <p class="genre">{genre}</p>
  <p>{description}</p>
  <h3><i class="fas fa-code" /> by {author} | {term}</h3>
  <a href={link} target="_blank">Play {title}</a>
</div>
