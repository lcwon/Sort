# 정렬 알고리즘

## 알고리즘 설명

정렬 알고리즘은 원소들을 번호순이나 사전 순서와 같이 일정한 순서대로 정렬하는 알고리즘이다. 정렬 알고리즘은 데이터의 정규화나 의미 있는 결과물을 생성하는데 유용하게 쓰인다.

## 정렬 알고리즘의 조건 

1. 출력은 비 내림차순
3. 출력은 입력을 재 배열하여 만든 순열



## 선택 정렬 알고리즘(SelectionSort)
### 코드 

```java
public class SelectionSort {

    public static int [] SelectionSort(int A[]) {
        int n = A.length;
        int temp;
        for (int i = 0; i < n - 1; i++) {
            int min = i;
            for (int j = i+1; j < n; j++) {
                if (A[j] < A[min]) {
                    min = j;
                }
            }
                temp = A[min];
                A[min] = A[i];
                A[i] = temp;
            }return A;
    }
}
```

선택 정렬 알고리즘은 정렬되지 않은 데이터들에 대해 가장 작은 데이터를 찾아 가장 앞의 데이터와 교환 해나가는 방식이다.


int n은 배열 `A`의 길이 이다. `temp` 가장 작은 값을 잠시 저장하는 값으로 정렬이 완료 될때까지 갱신되는 값이다.


### 성능분석
![](https://postfiles.pstatic.net/MjAyMTA1MDRfMjg3/MDAxNjIwMDk5Mjg4NTcy.EI9QtB_5bGUQPe4ZA9jl62ECbD9yDZJIxzukt2I2NnUg.THe0NZXu1evqPD-LlsYEwfuPJwRDWFJVn1eyRfi64BAg.PNG.codnjs060/image.png?type=w773)


![](https://postfiles.pstatic.net/MjAyMTA1MDRfMjg3/MDAxNjIwMDk5Mjg4NTcy.EI9QtB_5bGUQPe4ZA9jl62ECbD9yDZJIxzukt2I2NnUg.THe0NZXu1evqPD-LlsYEwfuPJwRDWFJVn1eyRfi64BAg.PNG.codnjs060/image.png?type=w773)

![](https://postfiles.pstatic.net/MjAyMTA1MDRfMjgx/MDAxNjIwMDk5MzIwOTIw.CE26oVs6m3-yDy4u0ie_o2boubx0xSmUKNF5aDb3IBcg.ekSsKO9E5_IIRks8E2Tx0K9L8Uv78hDJ_LopVYCjQ-wg.PNG.codnjs060/image.png?type=w773)

![](https://postfiles.pstatic.net/MjAyMTA1MDRfNTEg/MDAxNjIwMDk5MzMzNTMz.MXXilwrEAYugOu8eFysuwUcKAJJJyAliRqRUfB9nhZEg.i98L4PxUzgTSqHp2C83jupW1nxL5Z6QevRPffyq08csg.PNG.codnjs060/image.png?type=w773)

![](https://postfiles.pstatic.net/MjAyMTA1MDRfMjU4/MDAxNjIwMDk5MzQ2MjI2.qsFP1yD2AQOJtKD1Y3mSZBuESaf70BzknSwAUajsE3Ig.BFZGm8mI5KAIoAq9utfG_XVSBkozRjtMJZh-MRF4oaUg.PNG.codnjs060/image.png?type=w773)

![](https://postfiles.pstatic.net/MjAyMTA1MDRfMTMx/MDAxNjIwMDk5MzU2NjM0.mmS7NivGMtrGg7Sl2PqryTUnRS24WXkGASScVBipEHQg.RUYOZLTBXE8So9mOuFwrFWXZc03_-HVF-6iWqQK2SZQg.PNG.codnjs060/image.png?type=w773)
### 삽입정렬(InsertionSort)

```java
public class InsertionSort {
    public static int [] InsertionSort(int A[]){
        int n = A.length;
        int j = 0;
        for (int i = 1; i< n; i++){
            int CurrentElement = A[i];
            for (j = i-1;j>=0 && CurrentElement < A[j];j--){
                A[j + 1] = A[j];
            }
            A[j+1] = A[i];
        }return A;
    }
}
```

삽입 정렬은 아직 정렬되지 않은 임의의 데이터를 이미 정렬된 부분의 적절한 위치에 삽입해 가며 정렬하는 방식이다.

### 쉘 정렬 (ShellSort)

```java
public class ShellSort {
    public static int[] ShellSort(int A[]){
        int n = A.length;
        int h = 1;
        for (int i = h; i < n; i++){
            int CurrentElement = A[i];
            int j=i;
            while (j >= h && A[j-h] > CurrentElement){
                A[j] = A[j-h];
                j = j-h;
            }A[j] = CurrentElement;
        }return A;
            }
        }

```
