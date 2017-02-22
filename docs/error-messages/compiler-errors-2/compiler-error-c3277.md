---
title: "컴파일러 오류 C3277 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3277"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3277"
ms.assetid: 8ac5f476-e30c-4879-92c6-f03cdbd74045
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 컴파일러 오류 C3277
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

관리되지 않는 열거형 'enum'을\(를\) 관리되는 'type' 내부에 정의할 수 없습니다.  
  
 열거형이 관리되는 형식 내부에 잘못 정의되었습니다.  
  
 다음 샘플에서는 C3277 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3277a.cpp  
// compile with: /clr  
ref class A  
{  
   enum E {e1,e2};   // C3277  
   // try the following line instead  
   // enum class E {e1,e2};  
};  
  
int main()  
{  
}  
```  
  
 다음 샘플에서는 C3277 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3277b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
__gc class A  
{  
   enum E {e1,e2};   // C3277  
   // try the following line instead  
   // __value enum E {e1,e2};  
};  
  
int main()  
{  
}  
```