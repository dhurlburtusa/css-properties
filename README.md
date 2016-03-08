# css-properties

It is not uncommon to see a CSS class called `nowrap` which is declared as `white-space: nowrap`.  You'll find other similar classes in most major CSS frameworks such as Bootstrap.  For example, Bootstrap declares `pull-left` to be `float: left`.  It declares `hidden` to be `display: none !important` and so on.  These types of CSS classes are referred to as property-classes.

## How It All Began

After noticing this pattern many years ago, I thought "why not do something similar for almost all CSS properties"?  And that is how the idea for css-properties started.

## Naming Convention

All property/value pairs supported will have an associated class with the following syntax: {property-name}-{value}.  For instance, there is a class named `display-none` which is declared at `display: none !important`.  Some property/value pairs are associated with no than one class.  The declaration `display: none !important` is also associated with `hidden`.  This is done sparingly.

## Common Usage

Property-classes

## Advantages over Inline Styles

1) Shorter markup.  Compare the following three `div`s.  The first two use property-classes.  The last one uses inline styles.  In many cases, a `class` attribute already exists.  So, when using property-classes, there is no need to add a new style attribute.  Comparing the second `div` markup to the third `div` markup, there is a savings of 9 characters.  Comparing the first `div` markup to the third `div` markup, there is a savings of 15 characters.

    <div class="MyComponent  hidden">...</div>
    <div class="MyComponent  display-none">...</div>
    <div class="MyComponent" style="display: none;">...</div>

Some of the property-classes represent multiple declarations.  For example, the `display-flex` property-class uses several `display` declarations, each to handle the vendor specific values.

    <div class="display-flex">...</div>
    <div style="display: -moz-box; display: -webkit-box; display: -ms-flexbox; display: -webkit-flex; display: flex;">...</div>

Image trying to rememeber all those vendor specific property values over the simple property-class name.

2) Many times JavaScript is used to change the look of a component.  For example,  it is common to setup a button to expand and collapse a panel component.  When the panel is collapsed, it might have a `hidden` property-class.  When it is expanded, the `hidden` property-class is removed.  This is a common idiom and is especially useful when the class represents several property declarations.

3) A class can represent styles that are not possible with inline styles.  For example, there is no way to refer to pseudo-elements when using inline styles.

## FAQ

Q) Doesn't this effectively just move inline styles into CSS classes?
A) Sort of, but these property classes have advantages over inline styles.  See Advantages over Inline Styles above.
