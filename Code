.data
	world: .asciiz "Hello World"
	line: .asciiz "\n"
	fizz: .asciiz "FizzBuzz"
.text
#prints HelloWorld
la $a0, world
li $v0, 4
syscall
#prints FizzBuzz
la $a0, fizz
li $v0, 4
syscall
#Stores and adds two numbers from memory
li $t7, 10
li $t8, 20
sw $t7, 268500992
sw $t8, 268501024
lw, $t8, 268500992
lw $t7, 268501024
add $t8, $t8, $t7
sw $t8, 268501024
#sets registers for the loop
li $t0, -1
li $t1, 100
li $t2, 2
li $t3, 0
li $t4, 0
#prints all integers 1-100 and adds the even ones
loop:
	addi $t0, $t0, 1
	bgt $t0, $t1, exit
	move $a0, $t0
    	li $v0, 1
   	syscall
   	la $a0, line
   	li $v0, 4
   	syscall
   	div $t0, $t2
    	mfhi $t4
    	bne $t4, $zero, loop
    	add $t3, $t3, $t0
    	j loop
exit:
	move $a0, $t3
    	li $v0, 1
    	syscall
    	li $v0, 10
   	syscall
