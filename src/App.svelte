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
      <li>https://node-hnapi.herokuapp.com/news?page=number</li>
      <li>http://node-hnapi.herokuapp.com/item/$id</li>
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
        Create a file called Navigation.svelte file and import it into the
        App.svelte file.
      </li>
      <li>Add a link to "/" and some styling.</li>
      <li>Add it to the App.svelte file.</li>
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
      <li>Add the package to the App.svelte.</li>
      <li>Create a folder called "pages" in the "src" directory.</li>
      <li>
        Create two files called Home.svelte and SingleItem.svelte. (These will
        be our pages, if it was not already clear.)
      </li>
      <li>
        Wire everything together so that we have two routes. The paths on each
        route should be "/" and "/item/:id".
      </li>
    </ol>
    <h2>4. Building the Home page!</h2>
    <p>
      We'll now start building the home page. Here we will start fetching data.
      This is where we'll use the first of the two end-points. Using the
      built-in browser fetch API is probably the easiest. The result contains an
      array of stories. To start with we can just log these out. To dump the
      data an easy method is to just use a "pre" tag combined with a
      "JSON.stringify(data, undefined, 2)";.
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
      important ones are: url, title, id and comments_count. Don't forget to use
      the "Link" component from the 'svelte-routing' library. This will be
      needed to pass on the id to the SingleItem page.
    </p>
    <p>
      In the Home.svelte file where we have all the data. Use an #each to loop
      through the result array. Pass the data to the Headline component.
    </p>
    <h2>7. Wow! We're halfway there! I think?</h2>
    <p>
      Let's now build the SingleItem page! For now, let's, like before, just
      fetch the data and dump it on the page. This is where we'll use the second
      endpoint.
    </p>
    <p>
      Use a "pre" tag and dump it on the using the JSON.stringify method we used
      above. That's a lot of comments!? Study the contents of this and try to
      figure out the structure.
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
