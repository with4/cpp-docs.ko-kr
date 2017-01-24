---
title: "컴파일러 오류 C3803 | Microsoft Docs"
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
  - "C3803"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3803"
ms.assetid: bad5fb9a-ed9a-4c15-96e7-cf06e200a50d
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3803
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'property': 속성 형식이 해당 접근자 'accessor' 중 하나와 호환되지 않습니다.  
  
 [property](../../cpp/property-cpp.md)를 사용하여 정의한 속성 형식이 해당 접근자 함수 중 하나의 반환 형식과 일치하지 않습니다.  
  
 다음 샘플에서는 C3803 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3803.cpp  
struct A  
{  
   __declspec(property(get=GetIt)) int i;  
   char GetIt()  
   {  
      return 0;  
   }  
  
   /*  
   // try the following definition instead  
   int GetIt()  
   {  
      return 0;  
   }  
   */  
}; // C3803  
  
int main()  
{  
}  
```