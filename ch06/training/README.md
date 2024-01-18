### 독립된 파일 시스템 확인
    docker container run --name rn1 diamol/ch06-random-number
    docker container run --name rn2 diamol/ch06-random-number

    docker container cp rn1:/random/number.txt number1.txt
    docker container cp rn2:/random/number.txt number2.txt

### 이미지 레이어에 포함된 파일(컨테이너에 이미 존재하는 파일) 확인
    docker container run --name f1 diamol/ch06-file-display
    echo "http://eltonstoneman.com" > url.txt
    docker container cp url.txt f1:/input.txt
    docker container start --attach f1

    docker container run --name f2 diamol/ch06-file-display
    docker container rm -f f1
    docker container cp f1:/input.txt .