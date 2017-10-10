---
title: "컴파일러 오류 C3068 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3068
dev_langs:
- C++
helpviewer_keywords:
- C3068
ms.assetid: 613e3447-b4a8-4268-a661-297bed63ccdf
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 413376428e33cbc703b3371589777ba4fed0c1f7
ms.contentlocale: ko-kr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3068"></a>컴파일러 오류 C3068
'function': 'naked' 함수 해제가 필요한 c + + 예외가 발생 하는 개체를 포함할 수 없습니다  
  
 컴파일러에서 스택 해제를 수행할 수 없습니다. 한 [naked](../../cpp/naked-cpp.md) 함수 및 c + + 예외 처리에 임시 개체를 만들었기 때문에 예외가 발생 했습니다 함수 ([/EHsc](../../build/reference/eh-exception-handling-model.md)) 지정 되었습니다.  
  
 이 오류를 해결 하려면 다음 중 적어도 하나를 수행 합니다.  
  
-   /EHsc로 컴파일하지 않습니다.  
  
-   이 함수를 표시 하지 마십시오 `naked`합니다.  
  
-   함수에서 임시 개체를 만들지 마십시오.  
  
 함수를 만드는 경우 임시 개체는 스택에 함수가 예외를 throw 하 고 c + + 예외 처리를 사용 하는 경우 예외가 발생 하는 경우 컴파일러는 스택 정리 합니다.  
  
 예외가 발생 하 고 컴파일러에서 생성 한 코드를 프롤로그 라는 에필로그와에 없는 naked 함수, 함수에 대해 실행 됩니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3068 오류가 생성 됩니다.  
  
```  
// C3068.cpp  
// compile with: /EHsc  
// processor: x86  
class A {  
public:  
   A(){}  
   ~A(){}  
};  
  
void b(A){}  
  
__declspec(naked) void c() {  
   b(A());   // C3068   
};  
```
