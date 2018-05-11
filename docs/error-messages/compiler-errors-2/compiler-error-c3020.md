---
title: 컴파일러 오류 C3020 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3020
dev_langs:
- C++
helpviewer_keywords:
- C3020
ms.assetid: f625c7a3-afaa-4bd8-9c1b-51891b832f36
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2a9c942f6b1459cbdb88561b749290eb47d3cfb3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3020"></a>컴파일러 오류 C3020
'var': OpenMP 'for' 루프 인덱스 변수는 루프 본문에서 수정할 수 없습니다  
  
 OpenMP `for` 루프의 본문에 있는 인덱스 (루프 카운터)를 수정 하지 않을 수 있습니다는 `for` 루프입니다.  
  
 다음 샘플에서는 C3020 오류가 생성 됩니다.  
  
```  
// C3020.cpp  
// compile with: /openmp  
int main() {  
   int i = 0, n = 3;  
  
   #pragma omp parallel  
   {  
      #pragma omp for  
      for (i = 0; i < 10; i += n)  
         i *= 2;   // C3020  
         // try the following line instead  
         // n++;  
   }  
}  
```  
  
 선언 된 변수는 [lastprivate](../../parallel/openmp/reference/lastprivate.md) 병렬된 루프 내 인덱스로 사용 될 수 없습니다.  
  
 해당 lastprivate for 루프 내에서 가장 바깥쪽 idx_a 쓰기 트리거할 때문에 다음 샘플에 대 한 두 번째 lastprivate C3020를 제공 합니다. 첫 번째 lastprivate 해당 lastprivate 트리거합니다 (기술적으로 마지막 반복의 맨 끝)에 루프에 대 한 가장 바깥쪽 외부 idx_a에 쓰기 때문에 오류를 제공 하지 않습니다. 다음 샘플에서는 C3020 오류가 발생 합니다.  
  
```  
// C3020b.cpp  
// compile with: /openmp /c  
float a[100][100];  
int idx_a, idx_b;  
void test(int first, int last)  
{  
   #pragma omp parallel for lastprivate(idx_a)  
   for (idx_a = first; idx_a <= last; ++idx_a) {  
      #pragma omp parallel for lastprivate(idx_a)   // C3020  
      for (idx_b = first; idx_b <= last; ++idx_b) {  
         a[idx_a][idx_b] += 1.0f;  
      }  
   }  
}  
```  
  
 다음 샘플에는 가능한 해결 방법을 보여 줍니다.  
  
```  
// C3020c.cpp  
// compile with: /openmp /c  
float a[100][100];  
int idx_a, idx_b;  
void test(int first, int last)  
{  
   #pragma omp parallel for lastprivate(idx_a)  
   for (idx_a = first; idx_a <= last; ++idx_a) {  
      #pragma omp parallel for lastprivate(idx_b)  
      for (idx_b = first; idx_b <= last; ++idx_b) {  
         a[idx_a][idx_b] += 1.0f;  
      }  
   }  
}  
```