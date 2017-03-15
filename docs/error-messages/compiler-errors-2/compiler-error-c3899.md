---
title: "컴파일러 오류 C3899 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3899"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3899"
ms.assetid: 14e07e4a-f7a7-4309-baaa-649d69e12e23
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# 컴파일러 오류 C3899
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : 'class' 클래스의 병렬 영역 내부에서는 직접 initonly 데이터 멤버를 왼쪽 항의 값\(I\-value\)으로 사용할 수 없습니다.  
  
 [initonly](../../dotnet/initonly-cpp-cli.md) 데이터 멤버는 [parallel](../../parallel/openmp/reference/parallel.md) 영역에 있는 생성자의 일부 안에서 초기화할 수 없습니다.  컴파일러에서 이 코드를 내부적으로 재배치하여 이 코드가 사실상 생성자의 일부가 아닌 결과를 가져오기 때문입니다.  
  
 이 문제를 해결하려면 병렬 영역 외부가 아닌 생성자에서 initonly 데이터 멤버를 초기화합니다.  
  
## 예제  
 다음 샘플에서는 C3899 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3899.cpp  
// compile with: /clr /openmp  
#include <omp.h>   
  
public ref struct R {  
   initonly int x;  
   R() {  
      x = omp_get_thread_num() + 1000;   // OK  
      #pragma omp parallel num_threads(5)  
      {  
         // cannot assign to 'x' here  
         x = omp_get_thread_num() + 1000;   // C3899  
         System::Console::WriteLine("thread {0}", omp_get_thread_num());  
      }  
      x = omp_get_thread_num() + 1000;   // OK  
   }  
};  
  
int main() {  
   R^ r = gcnew R;  
   System::Console::WriteLine(r->x);  
}  
```