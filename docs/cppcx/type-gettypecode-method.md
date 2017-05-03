---
title: "Type::GetTypeCode 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Type::GetTypeCode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Type::GetTypeCode 메서드"
ms.assetid: 20c30432-91a3-400e-b9d6-eba265daaefc
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Type::GetTypeCode 메서드
기본 제공 형식의 숫자 형식 범주를 검색합니다.  
  
## 구문  
  
```cpp  
Platform::TypeCode GetTypeCode();  
```  
  
## 반환 값  
 Platform::TypeCode 열거형 값의 하나입니다.  
  
## 설명  
 `typeid` 속성은 GetTypeCode\(\) 멤버 메서드에 해당합니다.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **메타데이터:** platform.winmd  
  
## 참고 항목  
 [Platform::ValueType 클래스](../cppcx/platform-valuetype-class.md)