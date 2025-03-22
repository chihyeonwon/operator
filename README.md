# operator
실무용 연산자 정리 (filtering)

(s_ip  AND d_ip ) AND NOT (s_port AND d_port) ~

프로퍼티 별로 묶어서 쿼리 작성

쿼리 작성 시 숫자는 따옴표x 문자는 따옴표 포함, 대소문자 구별, NOT뒤에 띄어쓰기 X


이렇게 하면 쿼리 로직을 추가하기도 쉽고 튜닝하기 쉬워짐
## 연산자 교환 법칙 적용 됩니다.
(A AND B) AND C-> (A AND B OR C) 결합 법칙

## 로직 튜닝
# 비효율적인 방식
if is_heavy(item) and is_expensive(item):
    process(item)

# 효율적인 방식 (가벼운 연산 먼저 수행)
if is_expensive(item) and is_heavy(item):
    process(item)

# 일반 논리 연산
if (a % 2 == 0) and (b % 2 == 0):

# 비트 연산 활용 (짝수 검사는 마지막 비트가 0인지 확인)
if (a & 1 == 0) and (b & 1 == 0):
cache = {}

def is_valid(user):
    if user in cache:
        return cache[user]
    result = compute_validity(user)
    cache[user] = result
    return result
# 비효율적인 방식
if is_valid(user) and expensive_computation(user):
    approve(user)

# 최적화 방식
if not is_valid(user) or expensive_computation(user):
    approve(user)



논리 연산자를 튜닝하면 연산 속도, 메모리 사용량, 처리 효율을 향상시킬 수 있습니다.
📌 핵심 전략 정리

조건 순서 최적화 (빠른 연산 먼저)

Short-Circuit Evaluation 활용 (불필요한 연산 줄이기)

캐싱 기법 적용 (자주 참조되는 값 저장)

비트 연산 활용 (논리 연산을 비트 연산으로 변환)

## 포함, 제외 동일 조건

## 논리 연산자(검색용)
AND 
NOT
OR

like 
in 
## 와일드 카드(검색용)
%    
*      
