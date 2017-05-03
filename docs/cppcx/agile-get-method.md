---
title: "Agile::Get 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile::Get"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile::Get"
ms.assetid: d6295e21-ddbe-4302-9158-3498da4d9669
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Agile::Get 메서드
현재 Agile 개체가 나타내는 개체에 대한 핸들을 반환합니다.  
  
## 구문  
  
```cpp  
  
          T^ Get() const  
;  
```  
  
## 반환 값  
 현재 Agile 개체가 나타내는 개체에 대한 핸들입니다.  
  
 반환 값의 형식은 실제로 알려지지 않은 내부 형식입니다. 반환 값을 보유하는 편리한 방법은 [auto](~/cpp/auto-cpp.md) 형식 추론 키워드로 선언된 변수에 반환 값을 할당하는 것입니다. 예를 들어, `auto x = myAgileTvariable->Get();`을 입력합니다.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **헤더:** vccorlib.h  
  
## 참고 항목  
 [Platform::Agile 클래스](../cppcx/platform-agile-class.md)