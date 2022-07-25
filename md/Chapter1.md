# Source code

    ; db : define byte
    ; 512 byte를 0으로 정의합니다.
    times 510-($-$$) db 0
    ;그 중에서 0x55, 0xaa를 정의합니다.
    db 0x55, 0xaa
