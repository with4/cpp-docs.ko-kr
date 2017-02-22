---
title: "컴파일러 오류 C3183 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3183"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3183"
ms.assetid: dbd0f020-c739-43c9-947e-9ce21537331b
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 컴파일러 오류 C3183
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

WinRT 또는 관리되는 형식 'type' 내부에 명명되지 않은 클래스, 구조체 또는 공용 구조체를 정의할 수 없습니다.  
  
 WinRT 또는 관리되는 형식에 포함된 형식의 이름을 지정해야 합니다.  
  
 다음 샘플에서는 C3183 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3183a.cpp  
// compile with: /clr /c  
ref class Test  
{  
   ref class  
   {  // C3183, delete class or name it  
      int a;  
      int b;  
   };  
};  
```  
  
 다음 샘플에서는 C3183 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3183b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
__gc class Test  
{  
   __gc class  
   {  // C3183, delete class or name it  
      int a;  
      int b;  
   };  
};  
  
int main()  
{  
}  
```