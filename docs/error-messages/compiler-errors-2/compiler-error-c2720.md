---
title: "컴파일러 오류 C2720 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2720"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2720"
ms.assetid: 9ee3aab7-711b-4f5a-b2f1-cb62b130f1ce
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 오류 C2720
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier': 멤버에는 'specifier' 저장소 클래스 지정자를 사용할 수 없습니다.  
  
 선언 외부의 클래스 멤버에서 저장소 클래스를 사용할 수 없습니다.  이 오류를 해결하려면 클래스 선언 외부 멤버의 정의에서 불필요한 [저장소 클래스 지정자](http://msdn.microsoft.com/ko-kr/10b3d22d-cb40-450b-994b-08cf9a211b6c)를 제거합니다.  
  
 다음 샘플에서는 C2720 오류가 발생하는 경우 및 이를 해결하는 방법을 보여 줍니다.  
  
```  
// C2720.cpp  
struct S {  
   static int i;  
};  
static S::i;   // C2720 - remove the unneeded 'static' to fix it  
  
```