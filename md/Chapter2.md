# Source code

    mov ah, 0x0e
    mov al, 'A'
    ; interrupt 0x10(x87 Floating-Point Exception)
    ; 인위적으로 interrupt를 발생시킵니다.
    int 0x10

    loop:
        inc al ; +1 증가
        ; al이 'Z' + 1인지 검사합니다.
        cmp al, 'Z' + 1
        je exit
        int 0x10
        jmp loop

    exit:
        jmp $

    ; db : define byte
    ; 512 byte를 0으로 정의합니다.
    times 510-($-$$) db 0
    ;그 중에서 0x55, 0xaa를 정의합니다.
    db 0x55, 0xaa
