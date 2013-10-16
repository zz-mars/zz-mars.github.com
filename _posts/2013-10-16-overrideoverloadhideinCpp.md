---
layout: post
title: "override overload hide in C++"
description: "tech"
category: "Cpp"
tags: []
---
First,let's see an example of overload in C++ :
<pre>
#include<iostream>
void foo(int i) {}
void foo(float f) {}
void foo(double d) {}
int main()
{
	int i = 0;
	float f = 0.00;
	double d = 0.00;
	foo(i);
	foo(f);
	foo(d);
	return 0;
}
</pre>

Compile it to assembly :

{% include JB/setup %}

