---
title: "컴파일러 오류 C3463 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3463"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3463"
ms.assetid: 153efcc0-085c-4615-84ea-d22942618bdf
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# 컴파일러 오류 C3463
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type': 형식을 'implements' 특성에 사용할 수 없습니다.  
  
 [implements](../../windows/implements-cpp.md) 특성에 잘못된 형식이 전달되었습니다. 예를 들어 `implements`에 인터페이스를 전달할 수 있지만 포인터를 인터페이스에 전달할 수는 없습니다.  
  
## 예제  
 다음 샘플에서는 C3463을 생성합니다.  
  
```  
// C3463.cpp // compile with: /c #include <windows.h> [object, uuid("00000000-0000-0000-0000-000000000001")] __interface X {}; typedef X* PX; [ coclass, uuid("00000000-0000-0000-0000-000000000002"), implements(interfaces=PX) ]   // C3463 // try the following line instead // [ coclass, uuid("00000000-0000-0000-0000-000000000002"), implements(interfaces=X) ] class CMyClass : public X {};  
```