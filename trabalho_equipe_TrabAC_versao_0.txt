.data 
     entrada1: .asciiz "Forneça o primeiro inteiro "
     entrada2: .asciiz "Forneça o segundo inteiro "
.text 
     li $v0, 4
     la $a0, entrada1 #imprime a string entrada1
     syscall 
     
     li $v0, 5  #lê o primeiro inteiro
     syscall 
     
     move $t0, $v0 #move o inteiro de v0 pra t0
     
     li $v0, 4
     la $a1, entrada2 #imprime a string entrada2
     syscall 
     
     li $v0, 5 #lê o segundo inteiro
     syscall 
     
     move $t1, $v0 #move o inteiro de v0 pra t1
     
     bgt $t0,$t1, trocadeposicao #condicional pra trocar de posição
     
     li $v0, 10 #encerra o programa
     syscall 
     
     trocadeposicao:
        move $t2, $t0
        move $t0, $t1
        move $t1, $t2