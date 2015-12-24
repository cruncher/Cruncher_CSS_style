##Cruncher CSS style
	
#####1. Use classes to style, never IDs
Classes are reusable. IDs, not so much.

	.button {
		border-radius: 0.5rem;
	}

#####2. Extend classes by prefixing, using a dash to extend the class
Group base and extended classes together in your code.

	.button {
		border-radius: 0.5rem;
	}
	
	.action-button {
		display: block;
	}

#####3. Put media queries in mobile first order
And group media queries along with the classes they change.

	.button {
		border-radius: 0.5rem;
	}
	
	.action-button {
		display: block;
	}
	
	@media all and (min-width: 20em) {
		.action-button {
			display: inline-block;
		}
	}

#####4. Use context to modify layout
Generally speaking anything that affects style inside the border-box of an element should be described in a simple
class, while anything that affects layout outside of the border-box should be qualified with a context.

Be specific. Use child selectors to define positioning relative to a parent:

	.site-wrap > .logo-thumb {
		position: absolute;
		top: 0;
		left: 0;
	}

Use next sibling selectors to define space between pairs of elements:

	.logo-thumb + .button {
		margin-top: 1rem;
	}

Use both to define space between pairs in specific parents:

	.page-index > li + li {
		margin-left: 0.25rem;
	}

#####5. Prefer margin-top over margin-bottom, and margin-left over margin-right, for creating space between blocks
Top and bottom margins of blocks collapse (<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Mastering_margin_collapsing">except when they don't</a>). Left and right margins do not. Following this rule provides consistency. Break the rule only when you really know what you're doing.

	/* Create space between items in a button index. */
	.button-index > li + li {
		margin-top: 1rem;
	}

#####6. Use modifier classes to describe state
To avoid confusion with object classes, name modifier classes using past participles:

	.hidden
	.selected
	.disabled

Modifier classes should have no style of their own. Style is applied in combination with an object class:

	.button.selected {
		background-color: green;
	}

There are exceptions. For example, <code>.hidden</code> forces any element to be hidden:

	.hidden {
		display: none !important;
	}

#####7. Put all hacks in a separate stylesheet, hacks.css
In hacks.css you can break the rules.
