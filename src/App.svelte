<style>
  main {
    padding: 1em;
    margin: 0 auto;
  }

  .content {
    max-width: 600px;
    margin: 0 auto;
  }

  h1 {
    text-align: center;
    color: #ff3e00;
    text-transform: uppercase;
    font-size: 3em;
    font-weight: 100;
  }
  h2 {
    color: #ff3e00;
    font-size: 2em;
    font-weight: 100;
  }
  p,
  li {
    font-size: 18px;
    line-height: 22px;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

<main>
  <div class="content">
    <h1>HN Clone Code Along Instructions</h1>
    <p>
      Please follow along with the instructions and try to solve the problems
      that come up! We'll start off by cloning the svelte repository.
    </p>
    <p>
      These instructions are purposefully not 100% complete. The idea is that
      you should explore and learn while doing. I will semi-regularly be showing
      you solutions to each instruction as we go, so don't worry if you get
      stuck!
    </p>
    <p>
      The API that we will be using is called node-hnapi. There are two
      endpoints that are important here:
    </p>
    <ul>
      <li>
        <a target="_blank" href="https://node-hnapi.herokuapp.com/news?page=1">
          https://node-hnapi.herokuapp.com/news?page=1
        </a>
      </li>
      <li>
        <a target="_blank" href="http://node-hnapi.herokuapp.com/item/21741504">
          http://node-hnapi.herokuapp.com/item/21741504
        </a>
      </li>
    </ul>
    <p>Here are some resources to help you:</p>
    <ul>
      <li>
        <a target="_blank" href="https://svelte.dev/examples#hello-world">
          Examples Page
        </a>
      </li>
      <li>
        <a target="_blank" href="https://svelte.dev/docs">
          API Page (Documentation)
        </a>
      </li>
      <li>
        <a target="_blank" href="https://svelte.dev/tutorial/basics">
          Tutorial Page
        </a>
      </li>
    </ul>
    <p>
      If you want to, you can add styling to your code. In Svelte it's very
      simple to do. Just create a style tag and add your css. Easy-peasy!
    </p>
    <h2>1. Clone the project</h2>
    <p>
      To get start, visit the
      <a target="_blank" href="https://www.svelte.dev">Svelte website</a>
      and follow the instructions. If you can't, for some reason, manage to
      clone the Svelte project and get it running, you can use the
      <a
        target="_blank"
        href="https://svelte.dev/repl/hello-world?version=3.16.1">
        RELP
      </a>
      . Here you can do everything that we will do locally but online. .
    </p>
    <h2>2. Familiarize yourself with the code</h2>
    <p>
      Open the project in your preferred editor, and look around in the code. It
      should look very much like, for example, a React project.
    </p>
    <h2>3. Create your first component</h2>
    <p>Let's start off by creating our first component.</p>
    <ol>
      <li>Inside the source folder, create a components folder.</li>
      <li>
        Create a file called
        <b>Navigation.svelte</b>
        file and import it into the
        <b>App.svelte</b>
        file.
      </li>
      <li>
        Add a link to
        <b>"/"</b>
        and some styling.
      </li>
      <li>
        Add it to the
        <b>App.svelte</b>
        file.
      </li>
    </ol>
    <h2>4. Let's add a router!</h2>
    <p>
      Since Svelte doesn't have a router built-in we'll be using a third-party
      package for that. The one we'll be using is called
      <a target="_blank" href="https://github.com/EmilTholin/svelte-routing">
        svelte-routing
      </a>
      . You can find examples and usage instructions in the git repository.
    </p>
    <ol>
      <li>
        Add the package to the
        <b>App.svelte</b>
        .
      </li>
      <li>
        Create a folder called
        <b>pages</b>
        in the
        <b>src</b>
        directory.
      </li>
      <li>
        Create two files called
        <b>Home.svelte</b>
        and
        <b>SingleItem.svelte</b>
        . (These will be our pages, if it was not already clear.)
      </li>
      <li>
        Wire everything together so that we have two routes. The paths on each
        route should be
        <b>"/"</b>
        and
        <b>"/item/:id"</b>
        .
      </li>
    </ol>
    <h2>4. Building the Home page!</h2>
    <p>
      We'll now start building the home page. Here we will start fetching data.
      This is where we'll use the first of the two end-points. Using the
      built-in browser fetch API is probably the easiest. The result contains an
      array of stories. To start with we can just log these out. To dump the
      data an easy method is to just use a
      <b>pre</b>
      tag combined with a
      <b>JSON.stringify(data, null, 2)</b>
      .
    </p>
    <p>
      You have some options here. Ideally we want to show some kind of loading
      state while we fetch the data here. For that we can use the handy #await.
      Another way is to handle the loading state manually, like in for example,
      React.
    </p>
    <h2>6. We need a Headline component!</h2>
    <p>
      Create a Headline component that we can use to display each item in the
      results array from the last chapter. The result object contains a number
      of properties that you will have to pass on to the component. The
      important ones are:
      <b>url, title, id, comments_count</b>
      . Don't forget to use the
      <b>Link</b>
      component from the 'svelte-routing' library. This will be needed to pass
      on the id to the
      <b>SingleItem</b>
      page.
    </p>
    <p>
      In the Home.svelte file where we have all the data. Use an #each to loop
      through the result array. Pass the data to the Headline component.
    </p>
    <h2>7. Wow! We're halfway there! I think?</h2>
    <p>
      Let's now build the
      <b>SingleItem</b>
      page! For now, let's, like before, just fetch the data and dump it on the
      page. This is where we'll use the second endpoint.
    </p>
    <p>
      Use a
      <b>pre</b>
      tag and dump it on the using the JSON.stringify method we used above.
      That's a lot of comments!? Study the contents of this and try to figure
      out the structure.
    </p>
    <h2>8. Let's build a comment component.</h2>
    <p>
      This is the trickiest part of the code-along. We'll be building a
      recursive component. In order to solve this you should use the
      "svelte:self" component. You will find it in the documentation. To display
      the content you can use @html that can also be found in the documentation.
    </p>
    <h2>BONUS ROUND! Add transitions!</h2>
    <p>
      Wouldn't it be nice if there were some nice transitions on the page? Try
      to use the built-in svelte transitions to make some cool animation when
      the comments or headlines load.
    </p>
  </div>
</main>
