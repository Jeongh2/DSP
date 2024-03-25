arr = []

N = int(input("N : "))
for i in range(N):
    min_map = input(".")
    arr.append(list(map(int,min_map.split())))
#결과 담을 배열 초기화
result = [['' for _ in range(N)] for _ in range(N)]


# 상하좌우 대각선 이동 방향
directions = [(1, 0), (-1, 0), (0, 1), (0, -1), (1, 1), (-1, -1), (1, -1), (-1, 1)]

# 주변의 지뢰 개수 세기
for i in range(N):
    for j in range(N):
        if arr[i][j] == 1:  # 현재 위치가 지뢰인 경우
            result[i][j] = "*"
        else:
            count = 0
            # 주변의 지뢰 개수 세기
            for dx, dy in directions:
                ni, nj = i + dx, j + dy
                if 0 <= ni < N and 0 <= nj < N and arr[ni][nj] == 1:
                    count += 1
            result[i][j] = str(count)

# 결과 출력
for row in result:
    print(' '.join(row)



