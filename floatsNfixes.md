# Floats & Fixes

## Floats

Floats are used to shift a box to the left or to the right, it allows us to display content around that box. How to use floats?

See the output below, and remember that float shortens the line boxes. Take a look, you'll get what i mean in a second!

<iframe height="464" style="width: 100%;" scrolling="no" title="Float Show" src="https://codepen.io/sauravkk/embed/LYpJvrb?height=464&theme-id=dark&default-tab=result" frameborder="no" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/sauravkk/pen/LYpJvrb'>Float Show</a> by Saurav kumar
  (<a href='https://codepen.io/sauravkk'>@sauravkk</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

Not down the use of `float` property. Do note the **light purple bg-color of `p` running from behind the div that's floated**. It's interesting, Right?

Ohhh and do remember the margin.

## Clearing Floats

So, Remember I said you'll need something when you want to put stuff in ways other than normal flow!
But just think Are you really willing to risk all of your layout for setting one element in it's place?

Probably not, Right?

Once you floated an element, all of the following elements will wrap around that floated element until they wrap underneath and normal flow continues. If you don't want that, you need to clear the float.

You can do so using:

```
.clear {
    clear: both;
}
```

It'll clear both sides whether it be right! ot it be left! For specific clears use left for lefft floated element and right for right floated element.

This will help you have your elements start after the float. But what if you want to have something like:

<iframe height="657" style="width: 100%;" scrolling="no" title="Float usecase" src="https://codepen.io/sauravkk/embed/GRpXLGy?height=657&theme-id=dark&default-tab=result" frameborder="no" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/sauravkk/pen/GRpXLGy'>Float usecase</a> by Saurav kumar
  (<a href='https://codepen.io/sauravkk'>@sauravkk</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

What we use for these things is a Clear fix hack. How that's done!

### Clear Fix Hacks

What we can do is apply clear fix hacks which you can add even when you can't stuff to html. Most of services allow you to add custom CSS, So what we can do is add CSS Generated content, and settting that to clear both. Easy, Right?

Take a look below!

<iframe height="273" style="width: 100%;" scrolling="no" title="Clear Fix Hack" src="https://codepen.io/sauravkk/embed/pojOBKB?height=273&theme-id=dark&default-tab=result" frameborder="no" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/sauravkk/pen/pojOBKB'>Clear Fix Hack</a> by Saurav kumar
  (<a href='https://codepen.io/sauravkk'>@sauravkk</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

See it working yay!
Better than before and better in code. If you stll got doubts check Resources below.

### The Block Formatting Context

Another way to clear floats inside a box is to invoke something that is called Block Formatting Context (BFC) on the container that contains the floated element. A Block Formatting Context contains everything inside it, which would include floated items which can no longer poke out the bottom of the box. There are a few ways to force a BFC, the most common when clearing floats is to set the overflow property to have a value other than the default visible.

```
.container {
    overflow: auto;
}
```

Using overflow like this generally work, but, in certain cases you could end up with stupid scrollbars everywhere.
It also can look a little confusing in your stylesheet: Did you set overflow because you wanted scrollbars or just to gain this clearing ability?

To make intent clearer and prevent the creation of a BFC causing unwanted side effects, you can use `flow-root` as a value of the `display` property. The only thing that `display: flow-root` does is to create a BFC, thus clearing your floats with no other problems caused.

```
.container {
    display: flow-root;
}
```

<iframe height="267" style="width: 100%;" scrolling="no" title="BFC" src="https://codepen.io/sauravkk/embed/JjYaVZK?height=267&theme-id=dark&default-tab=result" frameborder="no" allowtransparency="true" allowfullscreen="true">
  See the Pen <a href='https://codepen.io/sauravkk/pen/JjYaVZK'>BFC</a> by Saurav kumar
  (<a href='https://codepen.io/sauravkk'>@sauravkk</a>) on <a href='https://codepen.io'>CodePen</a>.
</iframe>

### USAGE OF FLOATS(Before Grid and Flex)

Before Grid, Flex and other layout stuff came. Developers used to use floats(i.e, floating one box at other's side) to create grid like patterns. But I'd like you not to use them in production.

## Resources

- [The Clearfix: Force an Element To Self-Clear its Children](https://css-tricks.com/snippets/css/clear-fix/)
- [Understanding CSS Layout And BFC - Smashing Magazine](https://www.smashingmagazine.com/2017/12/understanding-css-layout-block-formatting-context/)
- [MDN Float Docs](https://developer.mozilla.org/en-US/docs/Web/CSS/float)
- [MDN Clear Docs](https://developer.mozilla.org/en-US/docs/Web/CSS/clear)
