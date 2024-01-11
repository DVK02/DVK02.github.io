---
layout: post
title: "Pragmatic Principles: A Pragmatic Approach - Duplication"
date: 2023-01-11 09:00:00 -0500
category: Computer Science
---
## Introduction

>Every piece of knowledge must have a single, unambiguous, authoritative
representation within a system.

The second chapter of [The Pragmatic Programmer](https://amzn.to/48ueL4S) by Andrew Hunt and David Thomas covers programming processes and ideas that are virtually universal. For this article, I will cover the first section, *The Evils of Duplication*, which warns against duplication of knowledge in your code. Duplicate code can increase the amount of time it takes to change or debug code, and should be avoided at all costs.
## Types of Duplication

- **Imposed duplication**: The environment "forces" the developer to duplicate.
- **Inadvertent duplication**: Developer doesn't realize they are duplicating.
- **Impatient duplication**: Developer is lazy.
- **Interdeveloper duplication**: Multiple developer's duplicate.
### Addressing Imposed Duplication

- **Write a code generator**
	- Use common metadata representation to define structures across multiple languages each time the software is built.
	- Generate tests programmatically from test specification document that reflect that latest updates made by a client.
- **Write documentation**
	- Use comments for high-level explanations, leave the low-level knowledge in the code.
	- Comments will become outdated, and code will become outdated even faster.
	- Untrustworthy comments are worse than no comments at all.
- **Language Issues**
	- For example, in C/C++ have header files that duplicate names and type information of exported variables, functions, and (for C++) classes.
	- Unfortunately the only defense against this is to be cognizant of the potential error.
	- For languages that require duplication, for example C/C++, use the header file to document implementation rather than the source files.

### Addressing Inadvertent Duplication

>Avoid unnormalized data.

- **A mistake in the design**
	- **Example from the distribution industry**: A truck class and a route class can both have a driver attribute. However, say a driver calls in sick and needs to be replaced. Both truck and route have to be updated. There are multiple solutions; revise the design - should a truck or a route have a driver? Should there be a third object that knits together truck and route?
- **Mutually dependent data**
	```c++
	class Line {
	public:
		Point start;
		Point finish;
		double distance;
	};
	```
	- The above code defined attribute `distance`, the value of which is dependent on the values of attributes `start` and `finish`.
	- The problem is that when `start` and/or `finish` get updated, we must *remember* to update distance.
	- Therefore, it is better to make `distance` a calculated field like so
```c++
class Line {
	public:
		Point start;
		Point finish;
		double distance() { return start.distanceTo(finish); }
};
```
- **Mutually dependent data drawbacks**
	- In the above example, calculating distance isn't an expensive operation. However, there may be cases where the performance cost of avoiding mutually dependent data is not worth it, and caching is required.
	- In these cases, it is fine to violate *DRY* so long as the violation is contained within the class/function, which at least guarantees a single point of violation.
	- Example below
```c++
class Line {
	private:
		bool changed;
		double distance;
		Point start;
		Point finish;
		
	public:
		void setStart(Point p) { start = p; changed = true; }
		void setFinish(Point p) { finish = p; changed = true; }
		Point getStart(void) { return start; }
		Point getFinish(void) { return end; }
		
		double getDistance() {
			if (changed) {
				distance = start.distanceTo(finish);
				changed = false;
			}
			return distance;
		}
};
```

*Note:* *Where possible, use accessor functions to read and write attributes of objects*.
### Impatient Duplication

>Shortcuts make for long delays.

- **Discipline**
	- Use discipline, usually there isn't an acceptable reason for impatient duplication.
### Interdeveloper Duplication

- **Interdeveloper Communication**
	- Either facilitated by a tech lead and clear design or other internal resources.
	- Have a central place in source tree for common utilities and scripts to be posted.
	- Get into the habit of reading other people's source code and documentation.
## Conclusion

If something isn't made easy to use, it wont be used, and very likely knowledge will be duplicated. The continuation of this chapter (part 2 of 3) will be found here.
## Tips

*Note: For Tips 1-10 check out the previous post.*

**Tip 11**: *DRY* - Don't Repeat Yourself.
**Tip 12**: Make it easy to reuse. 