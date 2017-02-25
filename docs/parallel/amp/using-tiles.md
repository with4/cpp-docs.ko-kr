---
title: "타일 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: acb86a86-2b7f-43f1-8fcf-bcc79b21d9a8
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# 타일 사용
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

바둑판식 배열을 사용하여 응용 프로그램의 가속을 최대화할 수 있습니다.  바둑판식 배열은 스레드를 동일한 사각형 하위 집합 또는 *타일*로 나뉩니다.  적절한 타일 크기와 바둑판식 알고리즘을 사용하는 경우 C\+\+ AMP 코드에서 더 많은 가속을 얻습니다.  바둑판식 배열의 기본 구성 요소는 다음과 같습니다.  
  
-   `tile_static` 변수.  바둑판식 배열의 가장 큰 이점은 `tile_static` 액세스로 인해 얻는 성능 향상입니다.  `tile_static` 메모리의 데이터 액세스는 전역 공간\(`array` 또는 `array_view` 개체\)의 데이터 액세스보다 상당히 빠를 수 있습니다.  `tile_static` 변수의 인스턴스는 각 타일에 대해 만들어지며 타일의 모든 스레드는 변수에 액세스할 수 있습니다.  일반적인 바둑판식 알고리즘에서 데이터는 전역 메모리에서 `tile_static` 메모리로 한 번 복사되고 나면 `tile_static` 메모리에서 여러 차례 액세스됩니다.  
  
-   [tile\_barrier::wait 메서드](../Topic/tile_barrier::wait%20Method.md).  `tile_barrier::wait`에 대한 호출은 같은 타일의 모든 스레드가 `tile_barrier::wait`에 대한 호출에 도달할 때까지 현재 스레드 실행을 일시 중단합니다.  스레드가 실행되는 순서를 보장할 수 없으며, 모든 스레드가 호출에 도달하기 전까지는 `tile_barrier::wait`에 대한 호출 이후에 타일의 스레드가 실행되지 않습니다.  `tile_barrier::wait` 메서드를 사용하면 스레드별 방식보다 타일별 방식으로 작업을 수행할 수 있습니다.  일반적인 바둑판식 알고리즘에는 `tile_barrer::wait`에 대한 호출에 이어 전체에 대해 `tile_static` 메모리를 초기화하는 코드가 있습니다.  `tile_barrier::wait` 뒤에 오는 코드에는 모든 `tile_static` 값에 대한 액세스가 필요한 계산이 포함됩니다.  
  
-   로컬 및 전역 인덱싱입니다.  전체 `array_view` 또는 `array` 개체에 상대적인 스레드 인덱스 및 타일에 상대적인 인덱스에 액세스할 수 있습니다.  로컬 인덱스를 사용하면 코드를 더 쉽게 읽고 디버깅할 수 있습니다.  일반적으로 `tile_static` 변수에 액세스하기 위해 로컬 인덱싱을 사용하고 `array` 및 `array_view` 변수에 액세스하기 위해 전역 인덱싱을 사용합니다.  
  
-   [tiled\_extent 클래스](../../parallel/amp/reference/tiled-extent-class.md)와 [tiled\_index 클래스](../../parallel/amp/reference/tiled-index-class.md)을 참조하십시오.  `parallel_for_each` 호출에서 `extent` 개체 대신에 `tiled_extent` 개체를 사용합니다.  `parallel_for_each` 호출에서 `index` 개체 대신에 `tiled_index` 개체를 사용합니다.  
  
 바둑판식 배열을 활용하려면 알고리즘은 더 빠른 액세스를 위해 계산 도메인을 타일로 분할한 후 타일 데이터를 `tile_static` 변수에 복사해야 합니다.  
  
## 전역, 타일 및 로컬 인덱스 예  
 다음 다이어그램은 2x3 타일에 정렬된 8x9 행렬의 데이터를 나타냅니다.  
  
 ![8x9 매트릭스를 2x3 바둑판식 배열로 분할](../../parallel/amp/media/usingtilesmatrix.png "UsingTilesMatrix")  
  
 다음 예제에는 바둑판식 매트릭스의 전역, 타일 및 로컬 인덱스가 표시됩니다.  `array_view` 개체는 `Description` 형식의 요소를 사용하여 만듭니다.  `Description`은 메트릭스 요소의 전역, 타일 및 로컬 인덱스를 포함합니다.  `parallel_for_each`에 대한 호출의 코드는 전역 값, 각 요소의 로컬 인덱스를 설정합니다.  출력 값으로 `Description` 구조체의 값이 표시됩니다.  
  
```cpp  
  
#include <iostream>  
#include <iomanip>  
#include <Windows.h>  
#include <amp.h>  
using namespace concurrency;  
  
const int ROWS = 8;  
const int COLS = 9;  
  
// tileRow and tileColumn specify the tile that each thread is in.  
// globalRow and globalColumn specify the location of the thread in the array_view.  
// localRow and localColumn specify the location of the thread relative to the tile.  
struct Description {  
    int value;  
    int tileRow;  
    int tileColumn;  
    int globalRow;  
    int globalColumn;  
    int localRow;  
    int localColumn;  
};  
  
// A helper function for formatting the output.  
void SetConsoleColor(int color) {  
    int colorValue = (color == 0) ? 4 : 2;  
    SetConsoleTextAttribute(GetStdHandle(STD_OUTPUT_HANDLE), colorValue);  
}  
  
// A helper function for formatting the output.  
void SetConsoleSize(int height, int width) {  
    COORD coord; coord.X = width; coord.Y = height;  
    SetConsoleScreenBufferSize(GetStdHandle(STD_OUTPUT_HANDLE), coord);  
    SMALL_RECT* rect = new SMALL_RECT();  
    rect->Left = 0; rect->Top = 0; rect->Right = width; rect->Bottom = height;  
    SetConsoleWindowInfo(GetStdHandle(STD_OUTPUT_HANDLE), true, rect);  
}  
  
// This method creates an 8x9 matrix of Description structures. In the call to parallel_for_each, the structure is updated   
// with tile, global, and local indices.  
void TilingDescription() {  
    // Create 72 (8x9) Description structures.  
    std::vector<Description> descs;  
    for (int i = 0; i < ROWS * COLS; i++) {  
        Description d = {i, 0, 0, 0, 0, 0, 0};  
        descs.push_back(d);  
    }  
  
    // Create an array_view from the Description structures.  
    extent<2> matrix(ROWS, COLS);  
    array_view<Description, 2> descriptions(matrix, descs);  
  
    // Update each Description with the tile, global, and local indices.  
    parallel_for_each(descriptions.extent.tile< 2, 3>(),  
         [=] (tiled_index< 2, 3> t_idx) restrict(amp)   
    {  
        descriptions[t_idx].globalRow = t_idx.global[0];  
        descriptions[t_idx].globalColumn = t_idx.global[1];  
        descriptions[t_idx].tileRow = t_idx.tile[0];  
        descriptions[t_idx].tileColumn = t_idx.tile[1];  
        descriptions[t_idx].localRow = t_idx.local[0];  
        descriptions[t_idx].localColumn= t_idx.local[1];  
    });  
  
    // Print out the Description structure for each element in the matrix.  
    // Tiles are displayed in red and green to distinguish them from each other.  
    SetConsoleSize(100, 150);  
    for (int row = 0; row < ROWS; row++) {  
        for (int column = 0; column < COLS; column++) {  
            SetConsoleColor((descriptions(row, column).tileRow + descriptions(row, column).tileColumn) % 2);  
            std::cout << "Value: " << std::setw(2) << descriptions(row, column).value << "      ";  
        }  
        std::cout << "\n";  
  
        for (int column = 0; column < COLS; column++) {  
            SetConsoleColor((descriptions(row, column).tileRow + descriptions(row, column).tileColumn) % 2);  
            std::cout << "Tile:   " << "(" << descriptions(row, column).tileRow << "," << descriptions(row, column).tileColumn << ")  ";  
        }  
        std::cout << "\n";  
  
        for (int column = 0; column < COLS; column++) {  
            SetConsoleColor((descriptions(row, column).tileRow + descriptions(row, column).tileColumn) % 2);  
            std::cout << "Global: " << "(" << descriptions(row, column).globalRow << "," << descriptions(row, column).globalColumn << ")  ";  
        }  
        std::cout << "\n";  
  
        for (int column = 0; column < COLS; column++) {  
            SetConsoleColor((descriptions(row, column).tileRow + descriptions(row, column).tileColumn) % 2);  
            std::cout << "Local:  " << "(" << descriptions(row, column).localRow << "," << descriptions(row, column).localColumn << ")  ";  
        }  
        std::cout << "\n";  
        std::cout << "\n";  
    }  
}  
  
void main() {  
    TilingDescription();  
    char wait;  
    std::cin >> wait;  
}  
  
```  
  
 예제의 주요 작업은 `array_view` 개체의 정의와 `parallel_for_each`에 대한 호출입니다.  
  
1.  `Description` 구조체의 벡터는 8 x 9 `array_view` 개체로 복사됩니다.  
  
2.  `parallel_for_each` 메서드는 `tiled_extent` 개체를 계산 도메인으로 사용하여 호출합니다.  `descriptions` 변수의 `extent::tile()` 메서드를 호출하여 `tiled_extent` 개체가 만들어집니다.  `extent::tile()`, `<2,3>`에 대한 호출의 형식 매개 변수는 지정 타일 2x3이 만들어지도록 지정합니다.  따라서 8x9 행렬은 12개의 타일, 4개의 행, 3개의 열에 배열됩니다.  
  
3.  `parallel_for_each` 메서드는 `tiled_index<2,3>` 개체\(`t_idx`\)를 인덱스로 사용하여 호출합니다.  인덱스의 형식 매개 변수\(`t_idx`\)는 계산 도메인의 형식 매개 변수\(`descriptions.extent.tile< 2, 3>()`\)와 일치해야 합니다.  
  
4.  각 스레드를 실행하면 `t_idx` 인덱스는 스레드가 있는 타일\(`tiled_index::tile` 속성\)과 타일 내 스레드의 위치\(`tiled_index::local` 속성\)에 대한 정보를 반환합니다  
  
## 타일 동기화—tile\_static and tile\_barrier::wait  
 이전 예제는 바둑판식 레이아웃 및 인덱스를 보여주지만 그 자체로는 별로 유용하지 않습니다.  바둑판식 배열은 타일이 알고리즘에 필수적이고 `tile_static` 변수를 활용할 때 유용합니다.  타일의 모든 스레드가`tile_static`변수에 액세스할 수 있기 때문에 `tile_barrier::wait`에 호출은 `tile_static`변수 액세스를 동기화하는 데 사용됩니다.  타일에 있는 모든 스레드는 `tile_static` 변수에 액세스할 수 있지만 타일에서 스레드 실행 순서는 보장되지 않습니다.  다음 예제에서는 `tile_static` 변수와 `tile_barrier::wait` 메서드를 사용하여 각 타일의 평균 값을 계산하는 방법을 보여 줍니다.  다음은 예제를 이해하기 위한 키입니다.  
  
1.  rawData는 8 x 8 매트릭스에 저장됩니다.  
  
2.  타일 크기는 2x2입니다.  그러면 4x4 표 형태 타일을 만들고 평균은 `array` 개체를 사용하여 4x4 행렬로 저장할 수 있습니다.  AMP 제한 함수에서 참조로 캡처할 수 있는 형식 수는 제한되어 있습니다.  `array` 클래스는 이러한 인수 중 하나입니다.  
  
3.  `array`, `array_view`, `extent` 및 `tiled_index`에 대한 형식 매개 변수는 상수 값이어야 하므로 메트릭스 크기와 샘플 크기는 `#define` 문을 사용하여 정의합니다.  또한 `const int static` 선언을 사용할 수도 있습니다.  추가 이점으로 4x4 타일에서 평균을 계산하기 위해 샘플 크기로 변경하는 것은 사소한 일입니다.  
  
4.  각 타일에 대해 `tile_static` 2x2 부동 값 배열이 선언됩니다.  선언은 모든 스레드에 대한 코드 경로에 있지만 매트릭스에 있는 각 타일에 대해 하나의 배열만 만들어집니다.  
  
5.  각 타일의 값을 `tile_static` 배열에 복사할 코드 줄이 있습니다.  값을 배열에 복사한 후 각 스레드에 대한 실행이 `tile_barrier::wait`에 대한 호출 때문에 중지됩니다.  
  
6.  특정 타일의 모든 스레드가 장애물에 도달하면 평균을 계산할 수 있습니다.  코드가 모든 스레드용으로 실행되기 때문에 오직 1개의 스레드 평균을 계산하기 위해서 `if` 문이 존재합니다.  평균은 평균 변수에 저장됩니다.  장벽은 기본적으로 `for` 루프를 사용할 수 있는 만큼 타일로 계산을 컨트롤하는 구성입니다.  
  
7.  `averages` 변수의 데이터는 `array` 개체이므로 호스트에 다시 복사되어야 합니다.  이 예제에는 벡터 변환 연산자가 사용됩니다.  
  
8.  전체 예제에서 SAMPLESIZE를 4로 변경하고 다른 변경 내용 없이 코드를 제대로 실행할 수 있습니다.  
  
```cpp  
  
#include <iostream>  
#include <amp.h>  
using namespace concurrency;  
  
#define SAMPLESIZE 2  
#define MATRIXSIZE 8  
void SamplingExample() {  
  
    // Create data and array_view for the matrix.  
    std::vector<float> rawData;  
    for (int i = 0; i < MATRIXSIZE * MATRIXSIZE; i++) {  
        rawData.push_back((float)i);  
    }  
    extent<2> dataExtent(MATRIXSIZE, MATRIXSIZE);  
    array_view<float, 2> matrix(dataExtent, rawData);  
  
    // Create the array for the averages.  
    // There is one element in the output for each tile in the data.  
    std::vector<float> outputData;  
    int outputSize = MATRIXSIZE / SAMPLESIZE;  
    for (int j = 0; j < outputSize * outputSize; j++) {  
        outputData.push_back((float)0);  
    }  
    extent<2> outputExtent(MATRIXSIZE / SAMPLESIZE, MATRIXSIZE / SAMPLESIZE);  
    array<float, 2> averages(outputExtent, outputData.begin(), outputData.end());  
  
    // Use tiles that are SAMPLESIZE x SAMPLESIZE.  
    // Find the average of the values in each tile.  
    // The only reference-type variable you can pass into the parallel_for_each call  
    // is a concurrency::array.  
    parallel_for_each(matrix.extent.tile<SAMPLESIZE, SAMPLESIZE>(),  
         [=, &averages] (tiled_index<SAMPLESIZE, SAMPLESIZE> t_idx) restrict(amp)   
    {  
        // Copy the values of the tile into a tile-sized array.  
        tile_static float tileValues[SAMPLESIZE][SAMPLESIZE];  
        tileValues[t_idx.local[0]][t_idx.local[1]] = matrix[t_idx];  
  
        // Wait for the tile-sized array to load before you calculate the average.  
        t_idx.barrier.wait();  
  
        // If you remove the if statement, then the calculation executes for every  
        // thread in the tile, and makes the same assignment to averages each time.  
        if (t_idx.local[0] == 0 && t_idx.local[1] == 0) {  
            for (int trow = 0; trow < SAMPLESIZE; trow++) {  
                for (int tcol = 0; tcol < SAMPLESIZE; tcol++) {  
                    averages(t_idx.tile[0],t_idx.tile[1]) += tileValues[trow][tcol];  
                }  
            }  
            averages(t_idx.tile[0],t_idx.tile[1]) /= (float) (SAMPLESIZE * SAMPLESIZE);  
        }  
    });  
  
    // Print out the results.  
    // You cannot access the values in averages directly. You must copy them  
    // back to a CPU variable.  
    outputData = averages;  
    for (int row = 0; row < outputSize; row++) {  
        for (int col = 0; col < outputSize; col++) {  
            std::cout << outputData[row*outputSize + col] << " ";  
        }  
        std::cout << "\n";  
    }  
    // Output for SAMPLESSIZE = 2 is:  
    //  4.5  6.5  8.5 10.5  
    // 20.5 22.5 24.5 26.5  
    // 36.5 38.5 40.5 42.5  
    // 52.5 54.5 56.5 58.5  
  
    // Output for SAMPLESIZE = 4 is:  
    // 13.5 17.5  
    // 45.5 49.5  
}  
  
int main() {  
    SamplingExample();  
}  
  
```  
  
## 경쟁 상태  
 다음과 같이 이름이 `total`인 `tile_static`이라는 변수 및 각 스레드에 대한 변수인 증분을 만들고자 할 수 있습니다.  
  
```cpp  
  
// Do not do this.  
tile_static float total;  
total += matrix[t_idx];  
t_idx.barrier.wait();  
averages(t_idx.tile[0],t_idx.tile[1]) /= (float) (SAMPLESIZE * SAMPLESIZE);  
  
```  
  
 이 방법을 사용할 경우 첫 번째 문제는 `tile_static` 변수가 이니셜라이저를 가질 수 없다는 것입니다.  두 번째 문제는 타일의 모든 스레드에 특정 순서 없이 변수에 대한 액세스 권한이 있으므로 `total`에 대한 할당에 경합 상태가 있다는 것입니다.  다음과 같이 하나의 스레드만 각 장벽의 합계에 액세스할 수 있도록 허용하는 알고리즘을 프로그래밍할 수 있습니다.  그러나 이 솔루션은 확장할 수 없습니다.  
  
```cpp  
  
// Do not do this.  
tile_static float total;  
if (t_idx.local[0] == 0 && t_idx.local[1] == 0) {  
    total = matrix[t_idx];  
}  
t_idx.barrier.wait();  
  
if (t_idx.local[0] == 0 && t_idx.local[1] == 1) {  
    total += matrix[t_idx];  
}  
t_idx.barrier.wait();  
  
// etc.  
  
```  
  
## 메모리 펜스  
 동기화되어야 하는 두 종류의 메모리 액세스는 전역 메모리 액세스 및 `tile_static` 메모리 액세스입니다.  `concurrency::array` 개체는 전역 메모리만 할당합니다.  `concurrency::array_view`는 생성된 방식에 따라 전역 메모리, `tile_static` 메모리 또는 둘 다를 참조할 수 있습니다.  동기화해야 하는 두 가지 종류의 메모리가 있습니다.  
  
-   전역 메모리  
  
-   `tile_static`  
  
 *메모리 펜스*는 스레드 파일의 다른 스레드가 메모리 액세스를 사용할 수 있고 메모리 액세스가 프로그램 순서에 따라 실행되도록 합니다.  이를 위해 컴파일러와 프로세서는 펜스에서 읽기 및 쓰기의 순서를 변경하지 않습니다.  C\+\+ AMP에서 메모리 펜스는 다음 메서드 중 하나를 호출하여 생성됩니다.  
  
-   [tile\_barrier::wait 메서드](../Topic/tile_barrier::wait%20Method.md): 전역 및 `tile_static` 메모리 주변에 펜스를 만듭니다.  
  
-   [tile\_barrier::wait\_with\_all\_memory\_fence 메서드](../Topic/tile_barrier::wait_with_all_memory_fence%20Method.md): 전역 및 `tile_static` 메모리 주변에 펜스를 만듭니다.  
  
-   [tile\_barrier::wait\_with\_global\_memory\_fence 메서드](../Topic/tile_barrier::wait_with_global_memory_fence%20Method.md): 전역 주변에만 펜스를 만듭니다.  
  
-   [tile\_barrier::wait\_with\_tile\_static\_memory\_fence 메서드](../Topic/tile_barrier::wait_with_tile_static_memory_fence%20Method.md): `tile_static` 메모리 주변에만 펜스를 만듭니다.  
  
 필요한 특정 펜스를 호출하면 앱의 성능이 향상될 수 있습니다.  barrier 형식은 컴파일러와 하드웨어의 문을 다시 정렬하는 방법에 영향을 줍니다.  예를 들어 전역 메모리 펜스를 사용하는 경우 펜스는 전역 메모리 액세스에 만 적용되어서 컴파일러와 하드웨어는 펜스의 양면에 있는 `tile_static` 변수에 읽기와 쓰기를 재명령합니다.  
  
 다음 예에서 장벽은 `tile_static` 변수인 `tileValues`에 쓰기를 동기화합니다.  이 예제에서 `tile_barrier::wait_with_tile_static_memory_fence`는 `tile_barrier::wait` 대신 호출됩니다.  
  
```cpp  
  
// Using a tile_static memory fence.  
parallel_for_each(matrix.extent.tile<SAMPLESIZE, SAMPLESIZE>(),  
     [=, &averages] (tiled_index<SAMPLESIZE, SAMPLESIZE> t_idx) restrict(amp)   
{  
    // Copy the values of the tile into a tile-sized array.  
    tile_static float tileValues[SAMPLESIZE][SAMPLESIZE];  
    tileValues[t_idx.local[0]][t_idx.local[1]] = matrix[t_idx];  
  
    // Wait for the tile-sized array to load before calculating the average.  
    t_idx.barrier.wait_with_tile_static_memory_fence();  
  
    // If you remove the if statement, then the calculation executes for every  
    // thread in the tile, and makes the same assignment to averages each time.  
    if (t_idx.local[0] == 0 && t_idx.local[1] == 0) {  
        for (int trow = 0; trow < SAMPLESIZE; trow++) {  
            for (int tcol = 0; tcol < SAMPLESIZE; tcol++) {  
                averages(t_idx.tile[0],t_idx.tile[1]) += tileValues[trow][tcol];  
            }  
        }  
        averages(t_idx.tile[0],t_idx.tile[1]) /= (float) (SAMPLESIZE * SAMPLESIZE);  
    }  
});  
  
```  
  
## 참고 항목  
 [C\+\+ AMP\(C\+\+ Accelerated Massive Parallelism\)](../../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md)   
 [tile\_static 키워드](../../cpp/tile-static-keyword.md)