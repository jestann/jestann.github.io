---
layout: post
title: Constant Aspect Ratio to a Div
date: 
---

12.15.17

Post to be finished.

Until I found this trick...

```
.outer {
	position: relative;
	width: 50%;		/* desired width */
}

.outer:before {
	content: '';
	display: block;
	padding-top: 100%; 	/* initial ratio of 1:1 ... 56.25% for 16:9 */
}

.inner-content {
	position:  absolute;
	top: 0;
	left: 0;
	bottom: 0;
	right: 0;
}
```

