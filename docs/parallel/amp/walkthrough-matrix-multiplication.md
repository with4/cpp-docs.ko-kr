---
title: "연습: 매트릭스 곱 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 61172e8b-da71-4200-a462-ff3a908ab0cf
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f91bed0b33ae29d7928ec7df3420eb4878b51eef
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-matrix-multiplication"></a>연습: 매트릭스 곱
이 단계별 연습 매트릭스 곱의 실행을 가속화 하 c + + AMP를 사용 하는 방법을 보여 줍니다. 두 알고리즘 바둑판식 배열 없는 및 바둑판식으로 표시 됩니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 시작하기 전에  
  
-   읽기 [c + + AMP 개요](../../parallel/amp/cpp-amp-overview.md)합니다.  
  
-   읽기 [타일을 사용 하 여](../../parallel/amp/using-tiles.md)합니다.  
  
-   다음 사항을 확인 [!INCLUDE[win7](../../build/includes/win7_md.md)], [!INCLUDE[win8](../../build/reference/includes/win8_md.md)], [!INCLUDE[winsvr08_r2](../../parallel/amp/includes/winsvr08_r2_md.md)], 또는 [!INCLUDE[winserver8](../../build/reference/includes/winserver8_md.md)] 컴퓨터에 설치 합니다.  
  
### <a name="to-create-the-project"></a>프로젝트를 만들려면  
  
1.  Visual Studio의 메뉴 모음에서 **파일**, **새로**, **프로젝트**합니다.  
  
2.  아래 **설치 됨** 템플릿 창에서 선택 **Visual c + +**합니다.  
  
3.  선택 **빈 프로젝트**, 입력 `MatrixMultiply` 에 **이름** 상자를 선택한 후는 **확인** 단추입니다.  
  
4.  **다음** 단추를 선택합니다.  
  
5.  **솔루션 탐색기**, 바로 가기 메뉴를 열고 **소스 파일**를 선택한 후 **추가**, **새 항목**합니다.  
  
6.  에 **새 항목 추가** 대화 상자에서 **c + + 파일 (.cpp)**, 입력 `MatrixMultiply.cpp` 에 **이름** 상자를 선택한 후는 **추가** 단추입니다.  
  
## <a name="multiplication-without-tiling"></a>바둑판식 배열 없이 곱하기  
 이 섹션에서는 ´ ï ´ ù A와 B 라는 두 행렬의 곱하기를 고려 합니다.  
  
 ![3 &#45; 여 &#45; 2 행렬](../../parallel/amp/media/campmatrixanontiled.png "campmatrixanontiled")  
  
 ![2 &#45; 여 &#45; 3 매트릭스](../../parallel/amp/media/campmatrixbnontiled.png "campmatrixbnontiled")  
  
 A는 3-2 매트릭스 및 B는 2-3 매트릭스가 나와 있습니다. B가 곱하는 A의 제품은 다음과 같은 3-3 매트릭스가 나와 있습니다. 제품 B 요소 열에 의해 A의 행을 곱하여 계산 됩니다.  
  
 ![3 &#45; 여 &#45; 3 매트릭스](../../parallel/amp/media/campmatrixproductnontiled.png "campmatrixproductnontiled")  
  
### <a name="to-multiply-without-using-c-amp"></a>C + + AMP를 사용 하지 않고 곱할  
  
1.  MatrixMultiply.cpp 열고 다음 코드를 사용 하 여 기존 코드를 바꿉니다.  
  
```cpp  
#include <iostream>  
  
void MultiplyWithOutAMP() {  
  
    int aMatrix[3][2] = {{1, 4}, {2, 5}, {3, 6}};  
    int bMatrix[2][3] = {{7, 8, 9}, {10, 11, 12}};  
    int product[3][3] = {{0, 0, 0}, {0, 0, 0}, {0, 0, 0}};  
  
    for (int row = 0; row < 3; row++) {  
        for (int col = 0; col < 3; col++) {  
            // Multiply the row of A by the column of B to get the row, column of product.  
            for (int inner = 0; inner < 2; inner++) {  
                product[row][col] += aMatrix[row][inner] * bMatrix[inner][col];  
            }  
            std::cout << product[row][col] << "  ";  
        }  
        std::cout << "\n";  
    }  
}  
  
void main() {  
    MultiplyWithOutAMP();  
    getchar();  
}  
```  
  
    The algorithm is a straightforward implementation of the definition of matrix multiplication. It does not use any parallel or threaded algorithms to reduce the computation time.  
  
2.  메뉴 모음에서 **파일**, **모두 저장**을 차례로 선택합니다.  
  
3.  디버깅을 시작 하 고 출력 올바른지 확인 하려면 F5 바로 가기 키를 선택 합니다.  
  
4.  응용 프로그램을 종료 하려면 enter 키를 선택 합니다.  
  
### <a name="to-multiply-by-using-c-amp"></a>C + + AMP를 사용 하 여 곱할  
  
1.  MatrixMultiply.cpp, 추가 앞에 다음 코드는 `main` 메서드.  
  
```cpp  
void MultiplyWithAMP() {  
    int aMatrix[] = { 1, 4, 2, 5, 3, 6 };  
    int bMatrix[] = { 7, 8, 9, 10, 11, 12 };  
    int productMatrix[] = { 0, 0, 0, 0, 0, 0, 0, 0, 0 };  
 
    array_view<int, 2> a(3, 2, aMatrix);

    array_view<int, 2> b(2, 3, bMatrix);

    array_view<int, 2> product(3, 3, productMatrix);

 
    parallel_for_each(product.extent,  
        [=] (index<2> idx) restrict(amp) {  
            int row = idx[0];  
            int col = idx[1];  
            for (int inner = 0; inner <2; inner++) {  
                product[idx] += a(row, inner)* b(inner, col);  
            }  
        });  
 
    product.synchronize();
 
    for (int row = 0; row <3; row++) {  
        for (int col = 0; col <3; col++) { 
            //std::cout << productMatrix[row*3 + col] << "  ";  
            std::cout << product(row, col) << "  ";  
        }    
        std::cout << "\n";  
    }  
}  
```  
  
    The AMP code resembles the non-AMP code. The call to `parallel_for_each` starts one thread for each element in `product.extent`, and replaces the `for` loops for row and column. The value of the cell at the row and column is available in `idx`. You can access the elements of an `array_view` object by using either the `[]` operator and an index variable, or the `()` operator and the row and column variables. The example demonstrates both methods. The `array_view::synchronize` method copies the values of the `product` variable back to the `productMatrix` variable.  
  
2.  다음 추가 `include` 및 `using` MatrixMultiply.cpp 맨 위에 있는 문.  
  
```cpp  
#include <amp.h>  
using namespace concurrency;  
```  
  
3.  수정 된 `main` 메서드를 호출 하는 `MultiplyWithAMP` 메서드.  
  
```cpp  
void main() {  
    MultiplyWithOutAMP();  
    MultiplyWithAMP();  
    getchar();  
}  
```  
  
4.  디버깅을 시작 하려면 Ctrl + F5 바로 가기 키를 선택 하 고 출력 올바른지 확인 하십시오.  
  
5.  응용 프로그램을 종료 하려면 스페이스바를 선택 합니다.  
  
## <a name="multiplication-with-tiling"></a>곱하기를 바둑판식 배열  
 바둑판식 배열에 같은 크기의 하위 집합으로, 타일 이라고 하는 데이터를 분할 기술입니다. 다음 세 가지 바둑판식 배열을 사용 하는 경우 변경 합니다.  
  
-   만들 수 있습니다 `tile_static` 변수입니다. 데이터에 대 한 액세스 `tile_static` 공간 보다 빠를 수 여러 번 전역 공간에서 데이터에 액세스할 수 있습니다. 인스턴스는 `tile_static` 각 타일에 대 한 변수 만들어지고 타일의 모든 스레드가 변수에 액세스할 수 있어야 합니다. 바둑판식 배열의 주요 장점은 성능 향상으로 인해 `tile_static` 액세스 합니다.  
  
-   호출할 수 있습니다는 [tile_barrier:: wait](reference/tile-barrier-class.md#wait) 메서드를 코드의 지정 된 줄에서 하나의 타일의 스레드가 모두 중지 합니다. 스레드에 실행 되는 순서를 보장할 수의 모든 타일이 하나에서 스레드가 호출 될 때 중지 됩니다 `tile_barrier::wait` 실행을 계속 있습니다.  

  
-   전체를 기준으로 스레드의 인덱스에 액세스할 수 있는 `array_view` 개체 및 타일 기준으로 인덱스입니다. 로컬 인덱스를 사용 하면 보다 쉽게 읽고 디버깅할 코드를 만들 수 있습니다.  
  
 를 사용 하려면 바둑판식 배열 매트릭스 곱의 알고리즘 행렬 바둑판식 배열로 분할 하며 다음 타일 데이터를 복사 `tile_static` 액세스 속도 대 한 변수입니다. 이 예제에서는 행렬은 동일한 크기의 submatrices로 분할 됩니다. 제품을는 submatrices 곱하여 찾을 수 있습니다. 두 매트릭스 및이 예에서 해당 제품입니다.  
  
 ![4 &#45; 여 &#45; 4 매트릭스](../../parallel/amp/media/campmatrixatiled.png "campmatrixatiled")  
  
 ![4 &#45; 여 &#45; 4 매트릭스](../../parallel/amp/media/campmatrixbtiled.png "campmatrixbtiled")  
  
 ![4 &#45; 여 &#45; 4 매트릭스](../../parallel/amp/media/campmatrixproducttiled.png "campmatrixproducttiled")  
  
 매트릭스는 다음과 같이 정의 된 4 개의 2x2 매트릭스로 분할 됩니다.  
  
 ![4 &#45; 여 &#45;분할 &#2; 45로; 하 여 4 행렬 &#45; 하위 2 &#45; 행렬](../../parallel/amp/media/campmatrixapartitioned.png "campmatrixapartitioned")  
  
 ![4 &#45; 여 &#45;분할 &#2; 45로; 하 여 4 행렬 &#45; 하위 2 &#45; 행렬](../../parallel/amp/media/campmatrixbpartitioned.png "campmatrixbpartitioned")  
  
 제품 a 및 B 이제 기록 고 다음과 같이 계산할 수 있습니다.  
  
 ![4 &#45; 여 &#45;분할 &#2; 45로; 하 여 4 행렬 &#45; 하위 2 &#45; 행렬](../../parallel/amp/media/campmatrixproductpartitioned.png "campmatrixproductpartitioned")  
  
 때문에 행렬 `a` 통해 `h` 2x2 행렬의 모든 제품 이므로 그중에서 합계도 2x2 행렬입니다. 또한 _ A * B는 4x4 매트릭스는 예상 대로 합니다. 알고리즘을 신속 하 게 확인 하려면 첫 번째 행의 요소, 제품의 첫 번째 열 값을 계산 합니다. 예제에서는 되는 요소의 값과 첫 번째 행의 첫 번째 열에 `ae + bg`합니다. 첫 번째 열, 첫 번째 행의 계산 하기만 하면 `ae` 및 `bg` 각 용어에 대 한 합니다. 해당 값에 대 한 `ae` 은 `1*1 + 2*5 = 11`합니다. 에 대 한 값 `bg` 은 `3*1 + 4*5 = 23`합니다. 최종 값은 `11 + 23 = 34`, 올바른지입니다.  
  
 이 알고리즘을 구현, 코드:  
  
-   사용 하 여 한 `tiled_extent` 개체가 아니라는 `extent` 개체에 `parallel_for_each` 호출 합니다.  
  
-   사용 하 여 한 `tiled_index` 개체가 아니라는 `index` 개체에 `parallel_for_each` 호출 합니다.  
  
-   만듭니다 `tile_static` 는 submatrices 저장 하기 위한 변수입니다.  
  
-   사용 하 여는 `tile_barrier::wait` 메서드는 submatrices 제품의 계산에 대 한 스레드를 중지 합니다.  
  
### <a name="to-multiply-by-using-amp-and-tiling"></a>사용 하 여 AMP 바둑판식 배열  
  
1.  MatrixMultiply.cpp, 추가 앞에 다음 코드는 `main` 메서드.  
  
```cpp  
void MultiplyWithTiling() {  
    // The tile size is 2.  
    static const int TS = 2;  

    // The raw data.  
    int aMatrix[] = { 1, 2, 3, 4, 5, 6, 7, 8, 1, 2, 3, 4, 5, 6, 7, 8 };  
    int bMatrix[] = { 1, 2, 3, 4, 5, 6, 7, 8, 1, 2, 3, 4, 5, 6, 7, 8 };  
    int productMatrix[] = { 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0 };  

    // Create the array_view objects.  
    array_view<int, 2> a(4, 4, aMatrix);  
    array_view<int, 2> b(4, 4, bMatrix);  
    array_view<int, 2> product(4, 4, productMatrix);  
  
    // Call parallel_for_each by using 2x2 tiles.  
    parallel_for_each(product.extent.tile<TS, TS>(),  
        [=] (tiled_index<TS, TS> t_idx) restrict(amp)   
        { 
            // Get the location of the thread relative to the tile (row, col) 
            // and the entire array_view (rowGlobal, colGlobal).  
            int row = t_idx.local[0];   
            int col = t_idx.local[1];  
            int rowGlobal = t_idx.global[0];  
            int colGlobal = t_idx.global[1];  
            int sum = 0;  
  
            // Given a 4x4 matrix and a 2x2 tile size, this loop executes twice for each thread.  
            // For the first tile and the first loop, it copies a into locA and e into locB.  
            // For the first tile and the second loop, it copies b into locA and g into locB.  
            for (int i = 0; i < 4; i += TS) {  
                tile_static int locA[TS][TS];  
                tile_static int locB[TS][TS];  
                locA[row][col] = a(rowGlobal, col + i);  
                locB[row][col] = b(row + i, colGlobal);  
                // The threads in the tile all wait here until locA and locB are filled.  
                t_idx.barrier.wait();  

                // Return the product for the thread. The sum is retained across 
                // both iterations of the loop, in effect adding the two products 
                // together, for example, a*e.  
                for (int k = 0; k < TS; k++) {  
                    sum += locA[row][k] * locB[k][col];  
                }  

                // All threads must wait until the sums are calculated. If any threads  
                // moved ahead, the values in locA and locB would change.        
                t_idx.barrier.wait();
                // Now go on to the next iteration of the loop.            
            }  
            
            // After both iterations of the loop, copy the sum to the product variable by using the global location.  
            product[t_idx.global] = sum;  
        });

    // Copy the contents of product back to the productMatrix variable.  
    product.synchronize();
 
    for (int row = 0; row <4; row++) {  
        for (int col = 0; col <4; col++) { 
            // The results are available from both the product and productMatrix variables. 
            //std::cout << productMatrix[row*3 + col] << "  ";  
            std::cout << product(row, col) << "  ";  
        }  
        std::cout << "\n";  
    }  
}  
```  
  
    This example is significantly different than the example without tiling. The code uses these conceptual steps:  
  
    1.  [0, 0]의 타일의 요소를 복사 `a` 에 `locA`합니다. [0, 0]의 타일의 요소를 복사 `b` 에 `locB`합니다. 다음에 유의 `product` 바둑판식으로 배열, 하지 `a` 및 `b`합니다. 따라서 전역 인덱스에 액세스 하려면 사용 `a, b`, 및 `product`합니다. 에 대 한 호출 `tile_barrier::wait` 필수적입니다. 둘 다를 때까지 모든 타일에서 스레드가 중지 `locA` 및 `locB` 채워집니다.  
  
    2.  곱하기 `locA` 및 `locB` 고 결과 `product`합니다.  
  
    3.  [0, 1]의 타일의 요소를 복사 `a` 에 `locA`합니다. [1, 0]의 타일의 요소를 복사 `b` 에 `locB`합니다.  
  
    4.  곱하기 `locA` 및 `locB` 에 이미 있는 결과에 추가할 `product`합니다.  
  
    5.  곱하기 [0, 0] 타일의 완료 되었습니다.  
  
    6.  다른 4 개의 타일에 대 한 반복 합니다. 인덱싱 타일에 맞게 되며 스레드 순서에 관계 없이 실행할 수 있습니다. 각 스레드가 실행 되는 `tile_static` 변수가 적절 하 게 각 타일에 대해 생성 된에 대 한 호출은 `tile_barrier::wait` 프로그램 흐름을 제어 합니다.  
  
    7.  알고리즘을 밀접 하 게 확인 하는 동안 확인 각 submatrix에 로드 되는 `tile_static` 메모리를 두 번입니다. 해당 데이터를 전송 하는 데 시간이 걸릴지 않습니다. 그러나 데이터에 있으면 `tile_static` 메모리, 데이터에 대 한 액세스는 훨씬 빠릅니다. 없기 때문에 제품을 계산 하려면는 submatrices의 값에 대 한 반복된 소요, 전반적인 성능 향상. 각 알고리즘에 대 한 최적의 알고리즘 찾기 및 타일 크기를 실험 필요 합니다.  
  
         비 AMP 및 비 타일 예제 A의 각 요소에서에서 제품을 계산 하는 전역 메모리에서 B 4 번 액세스 하 고 있습니다. 각 요소는 전역 메모리에서 두 번 들어오고 4 번 바둑판식 배열 예제에서는 액세스는 `tile_static` 메모리입니다. 상당한 성능 향상은 아닙니다. 그러나 A와 B가 1024 x 1024 행렬 및 타일 크기 된 16, 성능을 상당히 개선 됩니다. 에 각 요소는 복사 하는 경우 `tile_static` 메모리만 16 시간 및에서 액세스 `tile_static` 메모리 1024 시간입니다.  
  
2.  주 메서드를 호출 하도록 수정 된 `MultiplyWithTiling` 메서드를 표시 된 것 처럼 합니다.  
  
```cpp  
void main() {  
    MultiplyWithOutAMP();  
    MultiplyWithAMP();  
    MultiplyWithTiling();  
    getchar();  
}  
```  
  
3.  디버깅을 시작 하려면 Ctrl + F5 바로 가기 키를 선택 하 고 출력 올바른지 확인 하십시오.  
  
4.  응용 프로그램을 종료 하 고 스페이스바를 선택 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [C + + AMP (c + + Accelerated Massive Parallelism)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)   
 [연습: C++ AMP 응용 프로그램 디버깅](../../parallel/amp/walkthrough-debugging-a-cpp-amp-application.md)

