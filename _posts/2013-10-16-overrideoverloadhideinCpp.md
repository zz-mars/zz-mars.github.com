---
layout: post
title: "override overload hide in C++"
description: 
category: "Cpp"
tags: []
---

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

