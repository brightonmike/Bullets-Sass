![Alt text](https://cdn.rawgit.com/brightonmike/Bullets-Sass/master/bulletslogo.svg "Bullets sass logo")

# Bullets-Sass

[![Build Status](https://travis-ci.org/brightonmike/Bullets-Sass.svg?branch=button-no-border)](https://travis-ci.org/brightonmike/Bullets-Sass)

This is the pure Sass Bullets framework used in the Bullets WP starter theme.

`npm install bullets-sass`

### Sites built with Bullets

- http://www.pharmatsea.co.uk/ (Bullets version 1)
- http://formationfm.co.uk/
- https://www.chevronsandeclairs.com/ Built by Ryan Gittings https://ryangittings.co.uk/freelance-web-designer-london

Get started
===========

- Import Bullets into your project - place this in your `style.scss` in your assets.
  ```
  @import "settings";
  @import "../../node_modules/bullets-sass/scss/style";
  @include bullets-wordpress;

  @include bullets-grid;
  @include bullets-align;
  @include bullets-colour;
  @include bullets-touch;

  @include bullets-type;
  @include bullets-links;
  @include bullets-inputs;
  @include bullets-button;
  @include bullets-image;
  @include bullets-embed;

  @include bullets-forms;
  @include bullets-table;
  ```
    
- Create a settings file (copy from the package) and save as `_settings.scss` and place in the same location as your `style.scss` file.

- Import the mixins into the settings file, place this at the top.
  ```
  @import "../../node_modules/bullets-sass/scss/mixins";
  ```
  
  
### Basic Docs

- Get started by tweaking the settings in settings.scss
- You can remove or add the mixins in the style.scss file to only include what you need.
- Bullets has a 12 column grid with column classes for mobile, tablet and desktop, with the breakpoints of these controllable seperate to your media queries (though using the mqs by default).

### Getting Started With Gulp
- Run `npm update --save-dev` to update package.json dependencies to the latest and download the latest node modules.
- Run `gulp` to confirm everything is working

### Contribute

If you want to contribute - feel free. All pull requests considered. However, the aim of Bullets is to be light weight and skinny, so feature requests will always bare this in mind.


Grid
====

The Bullets grid is flexbox based, with browser support extended through Gulp. The grid is a tool and is as lightweight as possible. You should strongly consider when/how you are using it.

### Mark-up

```
<div class="row">
  <div class="column column-m-12 column-t-6 column-d-4">
  </div>
  <div class="column column-m-12 column-t-6 column-d-4">
  </div>
  <div class="column column-m-12 column-t-6 column-d-4">
  </div>  
</div>
```

Although the class names suggest "m" mobile, "t" tablet and "d" desktop, you should approach the use of the grid in a device agnostic manner.

### CSS Grid

Bullets comes with a helper for creating CSS Grids. You should include the mixin within a container class, for example:

```
.page {
    @include bullets-css-grid($column-min, $column-max, $row-min, $row-max, $grid-gap);
}
```

You shouldn't try to use one container to handle all your grids, or try to recreate a 12 column grid using CSS grid. Instead, use the mixin to help you create containers on parent elements such as whole pages. The Bullets CSS Grid auto-fills.

*Variables*
The mixin affects the following variables so you can define grid containers on the fly.

```
$column-min: 200px;
$column-max: 12fr;
$row-min: 150px;
$row-max: auto;
$grid-gap: 1rem;
```

To control the placement of elements within the grid, use the `grid-column` and `grid-row` properties. For example:

```
.header {
  grid-column: span 3;
}
```

This declaration tells the header to _span_ three columns. Equally:

```
.article {
  grid-row: span 4;
}
```

..Tells the article to _span_ four rows.

There are no pre-defined columns with CSS Grid as instead the layout of the columns is primarily defined by the parent.

### Constrain width

By default, Bullets is full width. Use the container class to constrain width.

```
<div class="container">
  <!-- grid -->
</div>
```

If you want to save mark-up, you can add it to the `row` element.

### Alignment

Use the row modifier classes to change alignment.

Horizontal:
```
.row--justified
.row--spaced
.row--end
.row--center
```

Vertical:
```
.row--middle
.row--bottom
.row--top
```

Buttons
=======

Bullets comes with a basic button component. You can adjust settings, including whether or not the button has a radius, in `settings.scss`.

### Markup

```
<button class="button">
  Button text
</button>
```

Strictly speaking, buttons should be buttons and links should be links. However, you can add the `.button` class to a link too. 

### Hollow 

Make a button hollow by adding the `.button--hollow` class.

Flexible Embeds
===============

Bullets comes with an `.embed` class. Add this to a `<div>` containing a video iframe or other object, and it will behave responsively. You may need to tweak to padding of `.embed` depending on aspect ratio.

### Inputs

Bullets comes with some basic input styling.

  
Icon from flaticon.com.
