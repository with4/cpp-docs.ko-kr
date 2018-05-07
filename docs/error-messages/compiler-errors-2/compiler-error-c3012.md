---
title: 컴파일러 오류 C3012 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3012
dev_langs:
- C++
helpviewer_keywords:
- C3012
ms.assetid: cc7040b1-b3fb-4da6-a474-877914d30332
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d30a7fbb50a984c8cec6b45a0ab4759a0578de7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3012"></a>컴파일러 오류 C3012
  
> '*내장*': 내장 함수 병렬 영역 내부에서는 직접 사용할 수 없습니다  
  
 A [컴파일러 내장 함수](../../intrinsics/compiler-intrinsics.md) 함수에서 허용 되지 않는 한 `omp parallel` 영역입니다. 이 문제를 해결 하려면 내장 함수는 영역 외부로 이동 하거나 비 내장 해당 항목으로 바꾸세요.   
  
## <a name="example"></a>예제  
  
 다음 샘플에서는 c 3012, 오류가 발생 하 고를 해결 하는 방법을 보여 줍니다.  
  
```cpp  
// C3012.cpp  
// compile with: /openmp  
#ifdef __cplusplus  
extern "C" {  
#endif  
void* _ReturnAddress();  
#ifdef __cplusplus  
}  
#endif  
  
int main()  
{  
   #pragma omp parallel  
   {  
      _ReturnAddress();   // C3012  
   }  
   _ReturnAddress();      // OK  
}  
```