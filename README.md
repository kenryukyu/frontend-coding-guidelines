# Universal Web Development Team Guidelines

Coding HTML, CSS, JS the way it was meant to be!

## Phase 1: Semantic HTML Development (HTML Developer)

### 1. Use proper HTML tags to define the meaning of the content on the page and components.

#### Grouping data and content

```html
<!--Sections of related content-->
<section>
  <header></header>
  <!-- section content -->
</section>
<!--Stand alone article-->
<article>
  <header></header>
  <!-- article content -->
</article>
<!-- Images with related content below (card) -->
<figure>
  <!-- image -->
  <figcaption></figcaption>
</figure>
<!-- Last resort groupings: -->
<div></div>
```

#### Tagging data

```html
- Titles:
<h1>
  ,
  <h2>
    ,
    <h3>
      …. - Basic Text Body Content:
      <p>
        - Time and dates:
        <time>
          - List of data:
          <ul>
            ,
            <ol>
              ,
              <li>
                - Definition list:
                <dl>
                  ,
                  <dt>,</dt>
                  <dd>
                    - Emphasize inline text:
                    <em>
                      - Table of data:
                      <table>
                        - Images:
                        <img />
                        - Last resort:
                        <span></span></table
                    ></em>
                  </dd>
                </dl>
              </li>
            </ol></ul
        ></time>
      </p>
    </h3>
  </h2>
</h1>
```

### 2. Add id’s, do not add classes yet to add more detailed meaning to the content

### 3. Create generic CSS skeleton similar to HTML

#### Example HTML

```html
<article>
  <header>
    <h3>My Article 1</h3>
    <time>1/2/2019</time>
  </header>
  <p id="basic_information">
    This is my article it is great.
  </p>
  <p id="very_important_information">
    This is another paragraph. It is important.
  </p>
</article>
```

#### Example CSS Skeleton

```scss
article {
  header {
    h3 {
    }
    time {
    }
  }

  p {
  }
}
```

### Don’t do’s:

Do not think about how the design looks at this phase. Also do not design HTML or define id/class names according to how the design looks visually. e.g.

```
<div class=“row c4”>
    <h2 class=“mat-h1 blue”>My Title</h2>
    <div class="col-2 left">Hi this is data.</div>
    <div class="col-2 right">And this is more data.</div>
</div>
```

## Phase 1: SASS Mixin Development for Design Elements (CSS Developer)

### 1. Create one “mixin” file, defining all elemental visual styles of the design using mixins. The mixin names should be descriptive in what the style looks like.

#### Example mixin with descriptive visual names:

```scss
@mixin big-blue-title() {
}
@mixin medium-red-title() {
}
@mixin small-black-title() {
}
@mixin small-grey-text() {
}
@mixin grey-bg-row-box() {
}
@mixin white-card() {
}
@mixin netflix-style-slider() {
}
@mixin basic-black-text(font-size) {
}
```

### 2. Create a “sampler” HTML page with each mixin example.

### Don’t do’s:

Do not be semantic with mixin names. e.g. @mixin main-title(), @mixin datetime(), @mixin software-section()

## Phase 2: Style the Design using Mixins and Specific Override CSS (HTML Developer & CSS Developer)

1. Inside CSS skeleton, apply mixins (HTML Developer or CSS Developer)

#### Example CSS

```scss
article {
  @include white-card();
  header {
    h3 {
      @include big-blue-title() l;
    }
    time {
      @include small-grey-text();
    }
  }

  p {
    @include basic-black-text(12);
  }
}
```

2. Add more CSS such as paddings, margins, floats, flex, absolutes, etc. to achieve the layout (CSS Developer)
3. Using id selectors defined in HTML, override specific sections for specific styling (CSS Developer)

```scss
article {
  @include white-card();
  header {
    h3 {
      @include big-blue-title() l;
    }
    time {
      @include small-grey-text();
    }
  }

  p {
    @include basic-black-text(12);

    &#very_imporant_data {
      font-weight: bold;
      color: red;
    }
  }
}
```

4. If more HTML tags are needed for styling or layout, ask HTML developer to add more semantic tags (HTML Developer)

## Phase 3: Refactor

1. After reviewing the code, see what can be re-used (HTML Developer & CSS Developer)
2. For re-usable styles, define semantic class names and refactor CSS. The class names should be semantic in meaning. (HTML Developer & CSS Developer)
