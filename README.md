# sass-baseline-rhythm

SASS mixins for creating a harmonious vertical rhythm.

These mixins are based on article by Jake Giltsoff: <http://typenot.es/posts/baseline-rem>.

## Install

Simply run the following within your project:

    $ bower install sass-baseline-rhythm
    
### application.scss file

    @import "../bower_components/sass-baseline-rhythm/_baseline-rhythm.scss";

## Syntax

    @mixin br__rootsize($rootsize);
    @mixin br__fontsize($val, $rootsize);

## Configuration

    $br__pixel-fallback: true; // if false pixel fallbacks won't be generated
    $br__rootsizes: (
      alpha: 12,
      beta: 14,
      gamma: 16,
      delta: 17,
      epsilon: 18
    );


## Usage

Please [read the article](http://typenot.es/posts/baseline-rem) for precise details on using this technique.

    html {
      @include br__rootsize; // or @include br__rootsize('alpha');

      @media (min-width: 35em) {
        @include br__rootsize('beta');
      }
      @media (min-width: 50em) {
          @include br__rootsize('gamma');
      }
    }

    p {
      line-height: 2rem;
      margin-bottom: 2rem;
      @include br__fontsize(16); // or @include br__fontsize(16, 'alpha');

      @media (min-width: 35em) {
        @include br__fontsize(18, 'beta');
      }
      @media (min-width: 50em) {
        @include br__fontsize(20, 'gamma');
      }
    }
