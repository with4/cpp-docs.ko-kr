---
title: "컴파일러 오류 C2297 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2297
dev_langs:
- C++
helpviewer_keywords:
- C2297
ms.assetid: 65849fe5-17e1-4b7e-b50c-f508b05ddaa4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d3f03bd9af2a8ca19a0715f8d423bcb7d3ff3c80
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2297"></a>컴파일러 오류 C2297
'operator': 잘못 된 오른쪽 피연산자  
  
 함께 사용 하는 오른쪽 피연산자 `operator` 올바르지 않습니다.  
  
 예를 들어 함수 호출 하려는 선언 컴파일러 표시 될 수 있습니다.  
  
 다음 샘플에서는 C2297 오류가 생성 됩니다.  
  
```  
// C2297.cpp  
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
  
   MyStruct m_MyStruct3 = m_MyStruct1 * m_MyStruct2;   // C2297  
}  
```