

<script>
  export let title;
  export let subtitle;
  export let description;
  export let imageUrl;
  export let address;
  export let contactEmail;

</script>
<style>
  article {
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
    border-radius: 5px;
    background: white;
    margin: 1rem;
  }

  header,
  .content,
  footer {
    padding: 1rem;
  }

  .image {
    width: 100%;
    height: 14rem;
  }

  .image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }

  h1 {
    font-size: 1.25rem;
    margin: 0.5rem 0;
    font-family: "Roboto Slab", sans-serif;
  }

  h1.is-favorite {
    background: #01a129;
    color: white;
    padding: 0 0.5rem;
    border-radius: 5px;
  }

  h2 {
    font-size: 1rem;
    color: #808080;
    margin: 0.5rem 0;
  }

  p {
    font-size: 1.25rem;
    margin: 0;
  }
</style>



<article>
  <header>
    <h1>{title}</h1>
    <h2>{subtitle}</h2>
  </header>
  <div class="image">
    <img src="{imageUrl}" alt="{title}" />
  </div>
  <div class="content">
    <p><b>Description:</b> {description}</p>
    <p><b>Address:</b> {address}</p>
    <p><b>Email:</b> <a href="mailto:{contactEmail}">Contact Email</a></p>
  </div>
  <footer>
    <button>Show Details</button>
    <button class="outline">Favorite</button>
  </footer>
</article>