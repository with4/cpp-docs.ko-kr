---
title: 컴파일러 오류 C3290 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3290
dev_langs:
- C++
helpviewer_keywords:
- C3290
ms.assetid: 0baf684b-1143-4953-ac99-a2fa267d8017
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bf65a35469ca978b0464c6f7275a6ac0e331da5d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3290"></a>컴파일러 오류 C3290
'type': trivial 속성은 참조 형식일 수 없습니다.  
  
 속성이 잘못 선언되었습니다. trivial 속성을 선언하면 컴파일러가 속성에서 업데이트할 변수를 만들며, 클래스에 추적 참조 변수를 사용할 수 없습니다.  
  
 참조 [속성](../../windows/property-cpp-component-extensions.md) 및 [추적 참조 연산자](../../windows/tracking-reference-operator-cpp-component-extensions.md) 자세한 정보에 대 한 합니다.  
  
## <a name="example"></a>예제  
 다음 샘플에서는 C3290을 생성합니다.  
  
```  
// C3290.cpp  
// compile with: /clr /c  
ref struct R {};  
  
ref struct X {  
   R^ mr;  
  
   property R % y;   // C3290  
   property R ^ x;   // OK  
  
   // OK  
   property R% prop {  
      R% get() {   
         return *mr;   
      }  
  
      void set(R%) {}  
   }  
};  
  
int main() {  
   X x;  
   R% xp = x.prop;  
}  
```