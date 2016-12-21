---
title: "컴파일러 오류 C3917 | Microsoft Docs"
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
  - "C3917"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3917"
ms.assetid: a24cd0c9-262f-46e5-9488-1c01f945933d
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3917
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'property': 사용되지 않는 construct 선언 스타일입니다.  
  
 속성 또는 이벤트 정의에 이전 버전의 구문이 사용되었습니다.  
  
 이전 버전의 구문을 사용하려면 [\/clr:oldSyntax](../../build/reference/clr-common-language-runtime-compilation.md)를 사용하십시오.  
  
 자세한 내용은 [속성](../../windows/property-cpp-component-extensions.md)을 참조하십시오.  
  
## 예제  
  
```  
// C3917.cpp  
// compile with: /clr /c  
public ref class  C {  
private:  
   int m_length;  
public:  
   C() {  
      m_length = 0;  
   }  
  
   property int get_Length();   // C3917  
  
   // The correct property definition:  
   property int Length {  
      int get() {  
         return m_length;  
      }  
  
      void set( int i ) {  
         m_length = i;  
      }  
   }  
};  
```