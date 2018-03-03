---
title: "컴파일러 경고 (수준 4) C4714 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4714
dev_langs:
- C++
helpviewer_keywords:
- C4714
ms.assetid: 22c7fd0c-899d-4e9b-95f3-725b2c49fb46
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5d49ff1bbf6538965d277b0afdd6c96fd9c71ef0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4714"></a>컴파일러 경고(수준 4) C4714
' function' 인라인이 아니라 __forceinline로 표시  
  
 인라인 확장에 대 한 지정된 된 함수를 선택 했지만 컴파일러 수행 하지 않은 인라인 처리 합니다.  
  
 하지만 `__forceinline` 보다 컴파일러에 보다 강력한 표시가 `__inline`인라인 처리, 컴파일러의 판단에 따라 계속 수행 있지만 없는 추론 사용의 이점을 결정를 인라인 처리이 함수입니다.  
  
 경우에 따라 컴파일러 인라인 처리 하지 않습니다는 특정 기능 기계적 이유로 합니다. 예를 들어, 컴파일러 인라인 처리 하지 않습니다.  
  
-   함께 SEH와 c + + EH 초래 하는 경우는 함수입니다.  
  
-   복사본과 일부 함수-GX EHs//eha 켜져 있을 때 값으로 전달 된 개체를 생성 합니다.  
  
-   -GX EHs//eha 켜져 있을 때 값으로 해제할 수 있는 개체를 반환 하는 함수입니다.  
  
-   없이-Og/Ox/O1/o 2를 컴파일할 때 인라인 어셈블리로 함수입니다.  
  
-   가변 인수 목록이 있는 함수입니다.  
  
-   사용 하는 함수는 **시도** 문 (c + + 예외 처리).  
  
 다음 샘플에서는 C4714 오류가 생성 됩니다.  
  
```  
// C4714.cpp  
// compile with: /Ob1 /GX /W4  
__forceinline void func1()  
{  
   try  
   {  
   }  
   catch (...)  
   {  
   }  
}  
  
void func2()  
{  
   func1();   // C4714  
}  
  
int main()  
{  
}  
```