# 정렬 알고리즘

## 알고리즘 설명

정렬 알고리즘은 원소들을 번호순이나 사전 순서와 같이 일정한 순서대로 정렬하는 알고리즘이다. 정렬 알고리즘은 데이터의 정규화나 의미 있는 결과물을 생성하는데 유용하게 쓰인다.

## 정렬 알고리즘의 조건 

1. 출력은 비 내림차순
3. 출력은 입력을 재 배열하여 만든 순열



## 버블 정렬 알고리즘(BubbleSort)
### 코드 설명
```java
public class BubbleSort {
    public static int[] BubbleSort(int[] A) {
        int n = A.length;
        for (int pass = 1; pass < n - 1; pass++) {
            for (int i = 0; i < n - pass; i++) {
                if (A[i] > A[i+1] ){
                    int temp = A[i];
                    A[i] = A[i + 1];
                    A[i+1] = temp;

                }
            }
        }
        return A;
    }
}
```
버블 정렬은 서로 이웃한 데이터들을 비교하며 가장 큰 데이터를 가장 뒤로 보내며 정렬하는 방식이다.
만약 A[0]이 A[1]보다 크면 A[0]은 `temp`에 저장되고 A[0]과 자리를 바꾼다.

 
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


## 삽입정렬(InsertionSort)

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
## 코드 설명
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
주어진 입력 파일의 매개 변수 갑에 까라 여러개의 부 파일로 나누고, 각 부파일은 삽입 정렬법으로 정렬하는 과정을 되풀이 하는 방법이다.


## main 
```java
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();

        int start = (int) System.currentTimeMillis();

        int A[] = new int[n];

        for (int i = 0; i < n; i++){
            A[i] = (int)(Math.random()*100000) + 1;
        }

        //System.out.println("정렬 전:" + Arrays.toString(A));

        //BubbleSort(A);
        //System.out.println("버블 정렬:" +Arrays.toString(A) );


        //SelectionSort(A);
        //System.out.println("선택 정렬 : " + Arrays.toString(A));


        //InsertionSort(A);
        //System.out.println("삽입 정렬 :" + Arrays.toString(A));

        ShellSort(A);
        System.out.println("쉘 정렬:" + Arrays.toString(A));


        int end = (int) System.currentTimeMillis();
        int processTime = end - start;
        System.out.printf("%d sec, %d ms", processTime / 1000, processTime % 1000);
    }
```
수행 시간을 기반으로 성능 평가를 하기 위해서 수월한 입력을 위해 배열 A에 n개의 난수를 생성한다.


### 성능분석

![](https://postfiles.pstatic.net/MjAyMTA1MDRfMTU0/MDAxNjIwMTAyMzI4ODkz.kZd6ulmm71S_OQhvTheGOgq6rnHFs7TgzLQlWV9TM5Yg.8wZCkv4zCdqdi-CKEm6yDltswo4h_FhchIssZ5KP3rAg.PNG.codnjs060/%EB%B2%84%EB%B8%94.png?type=w773)

버블 알고리즘

![](https://postfiles.pstatic.net/MjAyMTA1MDRfMjAx/MDAxNjIwMTAyMzI4ODcz.tQzpHsKGx-qXtykWnWlT3DuObUc85bjhKw1pSOnm2jsg.IeEa66egNQJIZbdvvcdRtzBS7mQ4RfXSbcaXLdvpMyMg.PNG.codnjs060/%EC%84%A0%ED%83%9D.png?type=w773)

선택정렬

![](https://postfiles.pstatic.net/MjAyMTA1MDRfMTQw/MDAxNjIwMTAyMzI4ODk5._Nq4ZNRe_yYKUWiHgZJMENKN8fQsiUiNo7oIJqbK3Dgg.B40Vgt5IeGsgQpuZc-T2F124g2DNkkTOn6x19ElgNpAg.PNG.codnjs060/%EC%82%BD%EC%9E%85.png?type=w773)


삽입정렬


![](https://postfiles.pstatic.net/MjAyMTA1MDRfNTcg/MDAxNjIwMTAyMzI4ODk1.I0Sh97rKGCAh3A9qV3EYk6u7DVDo-Gzqoc60Fo2LgDIg.3PR2xumGO1uVY9seMocMJbY7aVRJ1zfLQI7MNxUCT58g.PNG.codnjs060/%EC%89%98.png?type=w773)


셸 정렬

4개의 알고리즘의 수행 시간을 그래프로 표현하면 위와 같다. 내가 구현한 4개의 알고리즘 중에서 버블 정렬의 성능이 제일 떨어지고, 셸 정렬은 삽입 정렬을 변형한 알고리즘이지만 삽입 정렬의 성능이 가장 뛰어나다.
