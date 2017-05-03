---
title: "Guid::operator() 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Guid::operator()"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Guid::operator()"
  - "Platform, Guid::operator()"
ms.assetid: 5df51e6a-11c0-414c-8613-06b45a952828
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Guid::operator() 연산자
암시적으로 [GUID 구조체](http://msdn.microsoft.com/library/windows/desktop/aa373931\(v=vs.85\).aspx)GUID를 Platform::Guid로 변환합니다.  
  
## 구문  
  
```cpp  
Platform::Guid operator()  
```  
  
## 반환 값  
 Guid 구조체입니다.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **메타데이터:** platform.winmd  
  
## 참고 항목  
 [Platform::Guid 값 클래스](../cppcx/platform-guid-value-class.md)