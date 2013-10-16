---
layout: post
title: override & overload & hide in C++
description: 
category: "C++"
tags: []
---

----------------ol.cc----------------
<pre class="brush: cpp; title: ; notranslate" title="">#include <iostream>
using namespace std;
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

