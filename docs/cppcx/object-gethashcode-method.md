---
title: "Object::GetHashCode 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Object::GetHashCode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform, Object::GetHashCode"
ms.assetid: 403a60e9-be1d-4702-b14d-27fa4b2a043b
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Object::GetHashCode 메서드
COM 개체인 경우 이 인스턴스에 대한 [IUnknown](../atl/iunknown.md)\* ID 값을 반환하고, COM 개체가 아닌 경우 계산된 해시 값을 반환합니다.  
  
## 구문  
  
```cpp  
public:int GetHashCode()  
```  
  
## 반환 값  
 이 개체를 고유하게 식별하는 숫자 값입니다.  
  
## 설명  
 GetHashCode를 사용하여 맵에 개체의 키를 만들 수 있습니다.[Object::Equals 메서드](../cppcx/object-equals-method.md)를 사용하여 해시 코드를 비교할 수 있습니다. 코드 경로가 매우 중요하며 `GetHashCode` 및 `Equals`가 충분히 빠르지 않은 경우 기본 COM 레이어로 드롭다운하고 네이티브 [IUnknown](../atl/iunknown.md) 포인터 비교를 수행할 수 있습니다.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **헤더:** vccorlib.h  
  
## 참고 항목  
 [Platform::Object 클래스](../cppcx/platform-object-class.md)