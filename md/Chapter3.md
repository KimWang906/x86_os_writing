# Source code

    [org 0x7c00] ; 프로그램과 데이터의 시작 주소 설정
    mov ah, 0x0e
    mov bx, variableName

    printString:
        mov al, [bx]
        cmp al, 0
        je end
        int 0x10
        inc bx
        jmp printString

    end:
        jmp $

    variableName:
        ; db : define byte
        ; db = byte, dw = word, dd = double
        db "Hello, World!", 0

    ; 512 byte를 0으로 정의합니다.
    times 510-($-$$) db 0
    ;그 중에서 0x55, 0xaa를 정의합니다.
    db 0x55, 0xaa
