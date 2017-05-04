---
title: "String::IsFastPass 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::IsFastPass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::IsFastPass"
ms.assetid: 0a8c2db7-e44f-45fe-9570-3dc82fbbacdd
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::IsFastPass 메서드
현재 String 개체가 *빠른 전달* 작업에 참여하고 있는지를 나타냅니다. 빠른 전달 작업에서는 참조 횟수가 일시 중단됩니다.  
  
## 구문  
  
```cpp  
  
bool IsFastPass();  
```  
  
## 반환 값  
 현재 String 개체가 fast\-past이면 `true`이고, 그렇지 않으면 `false`입니다.  
  
## 설명  
 참조 횟수가 계산된 개체가 매개 변수이고, 호출된 함수가 이 개체만 읽는 함수에 대한 호출인 경우 컴파일러는 참조 횟수를 안전하게 일시 중단하고 호출 성능을 향상시킬 수 있습니다. 코드에서 이 속성으로 할 수 있는 유용한 일은 없습니다. 시스템에서 모든 세부 사항을 처리합니다.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **메타데이터:** vccorlib.h  
  
## 참고 항목  
 [Platform::String 클래스](../cppcx/platform-string-class.md)