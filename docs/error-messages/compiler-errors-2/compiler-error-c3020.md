---
title: "컴파일러 오류 C3020 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3020"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3020"
ms.assetid: f625c7a3-afaa-4bd8-9c1b-51891b832f36
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 오류 C3020
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : OpenMP 'for' 루프의 인덱스 변수는 루프 본문에서 수정할 수 없습니다.  
  
 OpenMP `for` 루프의 인덱스\(루프 카운터\)는 `for` 루프의 본문에서 수정할 수 없습니다.  
  
 다음 샘플에서는 C3020 오류가 발생하는 경우를 보여 줍니다.  
  
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
  
 [lastprivate](../../parallel/openmp/reference/lastprivate.md)를 사용하여 선언한 변수를 병렬화된 루프 내의 인덱스로 사용할 수 없습니다.  
  
 다음 샘플에서는 두 번째 lastprivate에 대해 C3020이 발생합니다. 이 lastprivate가 가장 바깥쪽 루프 내에서 idx\_a에 대한 쓰기를 트리거하기 때문입니다.  첫 번째 lastprivate는 오류를 발생시키지 않습니다. 이 lastprivate는 가장 바깥쪽 루프 외부\(일반적으로 마지막 반복의 끝\)에서 idx\_a에 대한 쓰기를 트리거하기 때문입니다.  다음 샘플에서는 C3020 오류가 발생하는 경우를 보여 줍니다.  
  
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
  
 다음 샘플에서는 가능한 해결 방법을 보여 줍니다.  
  
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