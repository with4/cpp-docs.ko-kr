---
title: "컴파일러 오류 C3815 | Microsoft Docs"
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
  - "C3815"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3815"
ms.assetid: c5a3b404-6341-4fd3-92af-152b404c4dde
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3815
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'get\_accessor' 메서드의 반환 형식은 setter의 마지막 매개 변수 형식과 일치해야 합니다.  
  
 [properties](../../misc/property.md)를 선언할 때 `get_accessor` 메서드의 반환 값은 set 접근자 메서드 선언의 마지막 매개 변수와 일치해야 합니다.  
  
 C3815는 **\/clr:oldSyntax**를 사용하는 경우에만 발생합니다.  
  
 다음 샘플에서는 C3815 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3815.cpp  
// compile with: /clr:oldSyntax /LD  
#using <mscorlib.dll>  
__gc class X  
{  
public:  
   __property char get_N()  
   // try the following line instead  
   // __property int get_N()  
   {  
      return m_val;  
   }  
  
   __property void set_N( int val)  
   {  
      m_val = val;  
   }  
  
private:  
   int m_val;  
};   // C3815  
```  
  
 다음 샘플에서는 getter의 반환 형식이 setter의 마지막 매개 변수와 일치하지 않도록 속성을 오버로드하는 경우를 보여 줍니다.  
  
```  
// C3815b.cpp  
// compile with: /clr:oldSyntax /c  
#using <mscorlib.dll>  
public __gc class MyClass {  
public:  
// 1st property:  
   __property System::Int32 get_p1();  
   __property void set_p1(System::Int32 i);  
  
// 2nd property (only setter):  
   __property void set_p1(System::Int32* i);  
  
};  
```