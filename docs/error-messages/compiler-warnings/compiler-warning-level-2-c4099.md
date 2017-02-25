---
title: "컴파일러 경고 (수준 2) C4099 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4099"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4099"
ms.assetid: 00bb803d-cae7-4ab8-8969-b46f54139ac8
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# 컴파일러 경고 (수준 2) C4099
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identifier' : 처음에는 'objecttype1'을\(를\) 사용하여 형식 이름을 표시했는데 이제는 'objecttype2'을\(를\) 사용하여 표시합니다.  
  
 구조체로 선언되는 개체가 클래스로 정의되었거나 클래스로 선언되는 개체가 구조체로 정의되었습니다.  컴파일러는 정의에 지정된 형식을 사용합니다.  
  
## 예제  
 다음 샘플에서는 C4099 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C4099.cpp  
// compile with: /W2 /c  
struct A;  
class A {};   // C4099, use different identifer or use same object type  
```