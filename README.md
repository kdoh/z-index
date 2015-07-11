# z-index
A tiny and dead simple set of CSS z-index utilities.

## why

The z space in CSS can easily become arbitrarily increased over time as new
components are added. You've probably seen something like this before in CSS
source code...

```css
/* need this to go above the other thing */
.og-component { z-index: 9; }
```
and some time later...
```css
/* this needs to go above og-component */
.new-component { z-index: 10; }
.newer-component { z-index: 11; }
```

In practice we generally don't need more than a few layers at any one time
even across fairly complex apps.

By adopting a small range of values that mimics the (inverse) of the HTML heading
spec, that we can apply directly to any html element, we prevent the need to
declare z-indexes on the fly, and keep the mental model of "layers" easy to
understand while developing.

```css
.z1 { z-index: 1; }
.z2 { z-index: 2; }
.z3 { z-index: 3; }
.z4 { z-index: 4; }
.z5 { z-index: 5; }
.z6 { z-index: 6; }
```

Other than the 6 basic indexes, a `zF` class is included that forces a very high
z-index in the event that another component or library is being overzealous
with its z-index values and you just can't even.

```css
.zF { z-index: 999; } /* break glass in case of emergency */
```

## usage

```html
<main>
    <section class="z1">I'm the lowest</section>
    <section class="z2">I'm a little bit higher.</section>
    <section class="z3">Chilling here in the middle, kinda hungry, could use a sandwich.</section>
    <section class="z4">Just a bit higher.</section>
    <section class="z5">I'm assistant to the highest z-index</section>
    <section class="z6">Look at me all the way up here.</section>

    <section class="zF">Buahaha and you thought z6 was high.</section>
</main>
```
