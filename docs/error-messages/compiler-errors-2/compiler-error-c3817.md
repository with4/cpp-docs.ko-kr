---
title: "컴파일러 오류 C3817 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3817"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3817"
ms.assetid: c6dbb57a-c65e-4040-8dd2-85bd9d4fd337
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3817
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'declaration': 속성은 함수에만 적용될 수 있습니다.  
  
 [property](../../misc/property.md) 키워드는 함수 정의에만 적용될 수 있습니다.  
  
 C3817은 **\/clr:oldSyntax**를 사용하는 경우에만 발생합니다.  
  
 다음 샘플에서는 C3817 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3817.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
__gc class G {  
      __property int x;   // C3817  
   };  
  
// the following class defines a property  
__gc class X {  
public:  
   __property int get_N( int i ) {  
      Console::WriteLine( L"int" );  
      return m_val[i];  
   }  
  
   __property void set_N( int i, int val ) {  
      m_val[i] = val;  
   }  
  
private:  
   int m_val[10];  
};  
  
int main() {  
}  
```