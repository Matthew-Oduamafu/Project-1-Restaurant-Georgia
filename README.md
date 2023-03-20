# Application Of SASS (Restaurant-Georgia)

**Table of content**

1. [SASS Variables](#sass-variables)
1. [SASS Mixins](#sass-mixins)

This project uses the power of [SASS](https://sass-lang.com/) to **_Transpile_** SASS code into css

#### SASS Variables

I made use of sass variables for define some commonly used `font-family`, `colors`, etc
that a repeated many places in the project.

example code snippet below

```scss
$color-primary: #d3ad55;
$color-secondary: #bbb;

// fonts
$font-dancingScript: "Dancing Script", "cursive";
$font-nunito: "Nunito", "sans-serif";
```

#### SASS Mixins

I used sass **Mixin** to group some css properties that can be apply to different elements. This way, the properties get declared ones and then applied wherever it is needed.

How to _mixins_:

```scss
@mixin flexLayouts() {
  display: flex;
  align-items: center;
  justify-content: center;
}

@mixin textStyles($transform: uppercase) {
  font-weight: 300;
  letter-spacing: 2px;
  text-transform: $transform;
}
```

How to apply _mixin_:

```scss
&-right {
  @include flexLayouts();
}
.nav-list {
  &-link {
    @include textStyles(capitalize);
  }
}
```

#### SASS Placeholders & Nesting

Sass placeholder is a way of implementing normal css multiple selectors

How to declare sass placeholder

```scss
%fullSpace {
  width: 100%;
  height: 100%;
}
```

Applying scss placeholder

```scss
.menu {
  @extend %fullSpace;
}
```

Sass Nesting can be used to apply style to a parent css selector and its child elements

```scss
.card {
  position: relative;

  &:hover .card-overlay {
    left: 0;
  }
  &-overlay {
    position: absolute;

    &-heading {
      @include textStyles(capitalize);
    }
    &-paragraph {
      @include textStyles(capitalize);
    }
    &-btn {
      width: 150px;
      height: 40px;
      color: $color-primary;
    }
  }
  &-img {
    @extend %fullSpace;
  }
}
```

[Click here to view site](https://georgia-restaurants.netlify.app/)



To view site click here [![website1](https://user-images.githubusercontent.com/72637895/224475267-5e7daa59-9435-4858-8b0a-236c8c7054eb.png)](https://georgia-restaurants.netlify.app/)




[![Short video of site](https://user-images.githubusercontent.com/72637895/226426549-98e04ab9-7198-4e30-8576-6c659858daae.mp4)](https://georgia-restaurants.netlify.app/)


