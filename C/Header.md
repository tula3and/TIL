## Headers

- `#include <stdio.h>` The essential
- `#include <string.h>`
  - `strlen()` 문자열 길이 반환
  - `memcpy(<save>, <copy>, <len>)` 문자배열 복사
  - `memchr(<where>, <char>, <len>)` `<char>` 이후의 문자열 전부 반환
  - `strcmp(<char>, <char>)` 두 문자열이 같으면 `0` 반환
- `#include <stdlib.h>`
  - `malloc` 동적 메모리 할당
    ```c
    int main() {
        int size;
        int *arr;

        printf("The number of factors: ");
        scanf("%d", &size);

        arr = (int *)malloc(sizeof(int) * size);
        // int arr[size];

        free(arr);

        return 0;
    }
    ```
  - `rand()` 0과 32767 사이의 임의의 정수 반환
    - 그러나 함수 호출 순서에 따라서 매번 일정한 수 반환
      - 그래서 `srand()`를 이용해 시드값을 바꾼다.
    - `rand() % (b - a + 1) + a` a와 b 사이의 난수 발생
  - `srand(<seed>)` 시드값이 다르면 난수가 달라짐
- `#include <time.h>`
  - `time(NULL)` 1970년 1월 1일 이후 현재까지 경과된 시간을 초 단위로 반환
- `#include <ctype.h>` 검사 후 참일 경우 0이 아닌 정수 반환
  - `isalpha()` 영문자 검사
  - `isupper()` `islower()` 대소문자 검사
  - `toupper()` `tolower()` 대소문자 변환
- `#include <stdarg.h>`
  - `va_list`, `va_start`, `va_arg`, `va_end`
  - 가변 인자를 `...`으로 선언
  - Example codes
    ```c
    double test_func(char* type, int count, ...) {
      int i;

      va_list argp;

      va_start(argp, count);

      double total = 0;

      if (type == "d") {
        for (i = 0; i < count; i++) {
          total += va_arg(argp, int);
        }
      }
      else if (type == "f") {
        for (i = 0; i < count; i++) {
          total += va_arg(argp, double);
        }
      }

      va_end(argp);

      return total / count;
    };
    ```
