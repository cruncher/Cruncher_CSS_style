##Cruncher CSS style
	
#####1. Use classes to style, never IDs
Classes are reusable. IDs, not so much.
	

	.button {
		border-radius: 0.5em;
	}
	
	
#####2. Extend classes by prefixing, using a dash to extend the class
Group base and extended classes together in your code.
	
	.button {
		border-radius: 0.5em;
	}
	
	.action-button {
		display: block;
	}
	
	
#####3. Put media queries in mobile first order
And use a media query for each group of classes that need to be made responsive.
	
	.button {
		border-radius: 0.5em;
	}
	
	.action-button {
		display: block;
	}
	
	@media all and (min-width: 20em) {
		.action_button {
			display: inline-block;
		}
	}
	
	
#####4. Use context to modify layout. Be specific. Use child selectors and next sibling selectors to define the contexts in which layout changes.
	
	.site-wrap > .logo-thumb {
		position: absolute;
		top: 0;
		left: 0;
	}
	
#####5. Prefer margin-top over margin-bottom, and margin-left over margin-right, for creating space between blocks
Top and bottom margins of blocks collapse – <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Mastering_margin_collapsing">although not in all cases</a>. Left and right margins do not. Following this rule provides consistency. Break the rule only when you really know what you're doing.

	.button-index > li {
		margin-top: 1em;
	}
	
	.button-index > li:first-child {
		margin-top: 0;
	}
	
#####6. Use past participle for state (or modifier) classes.

	.hidden
	.selected
	.highlighted

Usually modifier classes should have no style of their own. Style is applied in conjunction with an object class:

	.button.selected {
		background-color: green;
	}

There are exceptions. For example, <code>.hidden</code> should likely force an element to be hidden:

	.hidden {
		display: none !important;
	}

#####7. Put all hacks in a separate stylesheet, hacks.css
In hacks.css you can break the rules.
