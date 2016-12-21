---
title: "컴파일러 오류 C2612 | Microsoft Docs"
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
  - "C2612"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2612"
ms.assetid: 6faacfd6-4455-41a2-808e-0f6799f84d6d
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 컴파일러 오류 C2612
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

기본\/멤버 이니셜라이저 목록에 후행 'char'을\(를\) 사용할 수 없습니다.  
  
 이니셜라이저 목록에서 마지막 기본 또는 멤버 다음에 문자가 표시됩니다.  
  
 다음 샘플에서는 C2612 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2612.cpp  
class A {  
public:  
   int i;  
   A( int ia ) : i( ia ) + {};   // C2612  
};  
```