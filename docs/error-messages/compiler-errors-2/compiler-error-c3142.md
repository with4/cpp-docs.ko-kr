---
title: "컴파일러 오류 C3142 | Microsoft Docs"
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
  - "C3142"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3142"
ms.assetid: 795137ad-d00a-4a9c-9665-0cd8bfb5da8b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3142
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'property\_name' : 속성의 주소를 가져올 수 없습니다.  
  
 개발자는 속성의 주소를 사용할 수 없습니다.  
  
 다음 샘플에서는 C3142 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3142_2.cpp  
// compile with: /clr  
using namespace System;  
ref class CSize {  
private:  
   property int Size {  
      int get();  
   }  
};  
  
int main() {  
    &CSize::Size; // C3142  
}  
```  
  
 다음 샘플에서는 C3142 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3142.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
__gc class CSize  
{  
   __property int get_Size();  
};  
  
int main()  
{  
   &CSize::Size;   // C3142  
}  
```