---
title: "컴파일러 오류 C3161 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3161"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3161"
ms.assetid: 1fe2be85-a343-487b-8476-bf9e257eb29d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 컴파일러 오류 C3161
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'interface' : 인터페이스에 중첩 클래스, 구조체, 공용 구조체 또는 인터페이스를 사용할 수 없습니다. 클래스 구조체 또는 공용 구조체에 중첩 인터페이스를 사용할 수도 없습니다.  
  
 [\_\_interface](../../cpp/interface.md)는 네임스페이스 내부나 전역 범위에만 표시할 수 있습니다.  클래스, 구조체 또는 공용 구조체는 인터페이스에 표시할 수 없습니다.  
  
## 예제  
 다음 샘플에서는 C3161 오류가 발생하는 경우를 보여 줍니다.  
  
```  
// C3161.cpp  
// compile with: /c  
__interface X {  
   __interface Y {};   // C3161 A nested interface  
};  
```