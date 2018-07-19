---
title: 컴파일러 오류 C3899 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3899
dev_langs:
- C++
helpviewer_keywords:
- C3899
ms.assetid: 14e07e4a-f7a7-4309-baaa-649d69e12e23
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f40f1065514437463be06a89f01e067c4324cd2e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33275998"
---
# <a name="compiler-error-c3899"></a>컴파일러 오류 C3899
'var': 'class' 클래스에서 병렬 영역 내부에서는 직접 initonly 데이터 멤버의 l 값 사용은 사용할 수 없습니다  
  
 [initonly (C + + /cli CLI)](../../dotnet/initonly-cpp-cli.md) 해당 부분에 있는 생성자의 내부 데이터 멤버를 초기화할 수 없습니다는 [병렬](../../parallel/openmp/reference/parallel.md) 영역입니다.  생성자의 일부로 더 이상 효과적으로 되도록 컴파일러는 해당 코드의 내부는 재배치 때문입니다.  
  
 를 해결 하려면 병렬 영역 외부에 있으면 서 생성자에는 initonly 데이터 멤버를 초기화 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3899 오류가 발생 합니다.  
  
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