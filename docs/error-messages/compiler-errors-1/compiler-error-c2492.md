---
title: "컴파일러 오류 C2492 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2492"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2492"
ms.assetid: 8c44c9bb-c366-4fe5-a0ab-882e38608aaa
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# 컴파일러 오류 C2492
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'variable': 'thread' 데이터에 DLL 인터페이스를 사용할 수 없습니다.  
  
 변수가 DLL 인터페이스를 사용하여 [thread](../../cpp/thread.md) 특성을 통해 선언되었습니다.  `thread` 변수의 주소는 런타임이 되어야 알 수 있으므로 DLL 가져오기 또는 내보내기에 링크할 수 없습니다.  
  
 다음 샘플에서는 C2492 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C2492.cpp  
// compile with: /c  
class C {  
public:  
   char   ch;  
};  
  
__declspec(dllexport) __declspec(thread) C c_1;   // C2492  
__declspec(thread) C c_1;   // OK  
```