---
title: "컴파일러 오류 C3116 | Microsoft Docs"
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
  - "C3116"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3116"
ms.assetid: 597463e1-a5cc-4ed3-a917-eae9a61d3312
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C3116
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'storage specifier' : 인터페이스 메서드에 대한 저장소 클래스가 잘못되었습니다.  
  
 인터페이스 메서드에 대한 저장소 클래스로 `typedef`, `register` 또는 `static`을 사용했습니다.  인터페이스 멤버에는 이러한 저장소 클래스를 사용할 수 없습니다.  
  
 다음 샘플에서는 C3116 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3116.cpp  
__interface ImyInterface  
{  
   static void myFunc();   // C3116  
};  
```