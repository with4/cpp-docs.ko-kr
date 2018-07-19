---
title: 컴파일러 오류 C2296 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2296
dev_langs:
- C++
helpviewer_keywords:
- C2296
ms.assetid: 47d270f4-13ce-4c16-81e2-7d67c6c4a540
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c154073e0ea64527e444a7c46d13ba14ce05d63c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33171899"
---
# <a name="compiler-error-c2296"></a>컴파일러 오류 C2296
'operator': 잘못 된 왼쪽된 피연산자  
  
 왼쪽된 피연산자와 사용할 `operator` 올바르지 않습니다.  
  
 예를 들어 함수 호출 하려는 선언 컴파일러 표시 될 수 있습니다.  
  
 다음 샘플에서는 C2296 오류가 생성 됩니다.  
  
```  
// C2296.cpp  
struct MyStruct {  
   struct Help {  
      Help(float f) : m_f(f) {}  
      float m_f;  
   };  
  
   MyStruct(const Help &h) : m_f(h.m_f) {}  
   MyStruct(float f) : m_f(f) {}  
   MyStruct operator*(const MyStruct &f1) const {   
      return MyStruct(m_f * f1.m_f);  
   }  
  
private:  
   float m_f;  
};  
  
int main() {  
   float f1 = 1.0f;  
  
   MyStruct m_MyStruct1 ( MyStruct::Help( f1 ) );  
   // try the following line instead  
   // MyStruct m_MyStruct1 = MyStruct::Help( f1 );  
  
   MyStruct m_MyStruct2 ( MyStruct::Help( f1 ) );  
   // try the following line instead  
   // MyStruct m_MyStruct2 = MyStruct::Help( f1 );  
  
   MyStruct m_MyStruct3 = m_MyStruct1 * m_MyStruct2;   // C2296  
}  
```