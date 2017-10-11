---
title: "컴파일러 오류 C2217 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2217
dev_langs:
- C++
helpviewer_keywords:
- C2217
ms.assetid: 1ce1e3f5-4171-4376-804d-967f7e612935
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0f1795534af1332859fd1a33a137573df82643b4
ms.contentlocale: ko-kr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2217"></a>컴파일러 오류 C2217
'attribute1' 'attribute2' 필요  
  
 첫 번째 함수 특성에는 두 번째 특성이 필요 합니다.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>다음과 같은 가능한 원인을 확인하여 수정하려면  
  
1.  중단 (`__interrupt`)로 선언 된 함수 `near`합니다. 인터럽트 함수 여야 `far`합니다.  
  
2.  으로 선언 된 함수 인터럽트 `__stdcall`, 또는 `__fastcall`합니다. 함수를 중단 해야 사용 C 호출 규칙입니다.  
  
## <a name="example"></a>예제  
 C2217 가변 개수의 인수를 사용 하는 CLR 함수에 대리자를 바인딩할 사용 하려는 경우에 발생할 수 있습니다. 함수에 있는 경우 또한 e param 배열 오버 로드를 사용 하는 대신 합니다. 다음 샘플에서는 C2217 오류가 발생 합니다.  
  
```  
// C2217.cpp  
// compile with: /clr  
using namespace System;  
delegate void MyDel(String^, Object^, Object^, ...);   // C2217  
delegate void MyDel2(String ^, array<Object ^> ^);   // OK  
  
int main() {  
   MyDel2^ wl = gcnew MyDel2(Console::WriteLine);  
   array<Object ^ > ^ x = gcnew array<Object ^>(2);  
   x[0] = safe_cast<Object^>(0);  
   x[1] = safe_cast<Object^>(1);  
  
   // wl("{0}, {1}", 0, 1);  
   wl("{0}, {1}", x);  
}  
```
