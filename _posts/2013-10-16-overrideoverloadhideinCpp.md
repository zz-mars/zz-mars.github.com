---
layout: post
title: "override overload hide in C++"
description: "tech"
category: "Cpp"
tags: []
---
First,let's see an example of overload in C++ :
<pre>
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
<pre>
	.file	"ol.cc"
	.local	_ZStL8__ioinit
	.comm	_ZStL8__ioinit,1,1
	.text
	.globl	_Z3fooi
	.type	_Z3fooi, @function
_Z3fooi:
.LFB966:
	.cfi_startproc
	pushl	%ebp
	.cfi_def_cfa_offset 8
	.cfi_offset 5, -8
	movl	%esp, %ebp
	.cfi_def_cfa_register 5
	popl	%ebp
	.cfi_def_cfa 4, 4
	.cfi_restore 5
	ret
	.cfi_endproc
.LFE966:
	.size	_Z3fooi, .-_Z3fooi
	.globl	_Z3foof
	.type	_Z3foof, @function
_Z3foof:
.LFB967:
	.cfi_startproc
	pushl	%ebp
	.cfi_def_cfa_offset 8
	.cfi_offset 5, -8
	movl	%esp, %ebp
	.cfi_def_cfa_register 5
	popl	%ebp
	.cfi_def_cfa 4, 4
	.cfi_restore 5
	ret
	.cfi_endproc
.LFE967:
	.size	_Z3foof, .-_Z3foof
	.globl	_Z3food
	.type	_Z3food, @function
_Z3food:
.LFB968:
	.cfi_startproc
	pushl	%ebp
	.cfi_def_cfa_offset 8
	.cfi_offset 5, -8
	movl	%esp, %ebp
	.cfi_def_cfa_register 5
	subl	$8, %esp
	movl	8(%ebp), %eax
	movl	%eax, -8(%ebp)
	movl	12(%ebp), %eax
	movl	%eax, -4(%ebp)
	leave
	.cfi_restore 5
	.cfi_def_cfa 4, 4
	ret
	.cfi_endproc
.LFE968:
	.size	_Z3food, .-_Z3food
	.globl	main
	.type	main, @function
main:
.LFB969:
	.cfi_startproc
	pushl	%ebp
	.cfi_def_cfa_offset 8
	.cfi_offset 5, -8
	movl	%esp, %ebp
	.cfi_def_cfa_register 5
	andl	$-8, %esp
	subl	$24, %esp
	movl	$0, 20(%esp)
	movl	$0x00000000, %eax
	movl	%eax, 16(%esp)
	fldz
	fstpl	8(%esp)
	movl	20(%esp), %eax
	movl	%eax, (%esp)
	call	_Z3fooi
	movl	16(%esp), %eax
	movl	%eax, (%esp)
	call	_Z3foof
	fldl	8(%esp)
	fstpl	(%esp)
	call	_Z3food
	movl	$0, %eax
	leave
	.cfi_restore 5
	.cfi_def_cfa 4, 4
	ret
	.cfi_endproc
.LFE969:
	.size	main, .-main
	.type	_Z41__static_initialization_and_destruction_0ii, @function
_Z41__static_initialization_and_destruction_0ii:
</pre>

{% include JB/setup %}

