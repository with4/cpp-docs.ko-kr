---
title: "컴파일러 오류 C3818 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3818"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3818"
ms.assetid: f9502f6a-0690-4135-ab88-cc97cf490f5c
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C3818
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'property1' 배열 속성 선언은 'property2' 인덱스 속성을 오버로드하지 않습니다.  
  
 하나는 인덱서이고 다른 하나는 배열 속성인 경우에는 속성을 오버로드할 수 없습니다.  자세한 내용은 [\_\_property](../../misc/property.md)를 참조하십시오.  
  
 C3818은 **\/clr:oldSyntax**를 사용하는 경우에만 발생합니다.  
  
 다음 샘플에서는 C3818 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3818.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
__gc class X {  
public:  
   __property int get_Int(int index) {  
      Console::WriteLine(S"Called indexed property");  
      return m_value;  
   }  
  
   __property int get_Int() __gc[] {   // C3818, rename a property  
      Console::WriteLine(S"Called array property");  
      return m_arr;  
   }  
  
   int m_arr __gc[];  
   int m_value;  
};  
  
int main() {  
   X* x = new X;  
   x->m_arr = new int __gc[3];  
   x->m_value = 3;  
  
   x->Int[0];  
}  
```