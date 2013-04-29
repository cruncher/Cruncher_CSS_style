###CSS styleguide
	
	/* 1. Use classes to style, never ids. This is key to
	      writing modular CSS. */
	
	.button {
	  border-radius: 0.5em;
	}
	
	
	/* 2. Extend classes by prefixing, using an underscore to
	      denote a class extension, and group extended classes
	      and base classes together. */
	
	.button {
		border-radius: 0.5em;
	}
	
	.action_button {
		display: block;
	}
	
	
	/* 3. Put media queries in mobile first order, and use
	      a media query for each class that needs to be made
	      responsive, keeping them close together in the code. */
	
	.button {
		border-radius: 0.5em;
	}
	
	.action_button {
		display: block;
	}
	
	@media all and (min-width: 20em) {
		.action_button {
			display: inline-block;
		}
	}
	
	
	/* 4. Use child selectors to set positions and layouts. */
	
	.site_wrap > .logo_thumb {
		position: absolute;
		top: 0;
		left: 0;
	}
	
	
	/* 5. Prefer margin-top over margin-bottom, and margin-left
	      over margin-right, for creating space between blocks. */
	
	.button_index > li {
		margin-top: 1em;
	}
	
	.button_index > li:first-child {
		margin-top: 0;
	}
	
	
	/* 6. Namespace typography. */
	
	.typo1 {
		font-size: 0.9375rem; /* 15px */
		line-height: 1.4em;   /* 21px */
	}
	
	.typo1 h1,
	.typo1 h2,
	.typo1 h3 {
		font-weight: bold;
	}
	
	.typo1 p {
		margin-top: 0.6em;    /* 9px */
	}
	
	.typo1 h1:first-child,
	.typo1 h2:first-child,
	.typo1 h3:first-child,
	.typo1 p:first-child {
		/* Remove margin-top from first children of typo block. */ 
		margin-top: 0;
	}
	
	
	/* 7. Put all hacks in a separate stylesheet, hacks.css. In
	      hacks.css you can break the rules. */
