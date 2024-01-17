### 독립된 파일 시스템 확인
    docker container run --name rn1 diamol/ch06-random-number
    docker container run --name rn2 diamol/ch06-random-number

    docker container cp rn1:/random/number.txt number1.txt
    docker container cp rn2:/random/number.txt number2.txt