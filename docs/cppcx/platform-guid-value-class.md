---
title: "Platform::Guid 값 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Guid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Guid 구조체"
ms.assetid: 25c0bfb2-7f93-44d8-bdf4-ef4fbac3424a
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 6
---
# Platform::Guid 값 클래스
Windows 런타임 형식 시스템의 [GUID](http://msdn.microsoft.com/library/windows/desktop/aa373931\(v=vs.85\).aspx) 형식을 나타냅니다.  
  
## 구문  
  
```cpp  
public value struct Guid  
```  
  
## 멤버  
 Guid에는 [Platform::Object 클래스](../cppcx/platform-object-class.md)[Platform::Type 클래스](../cppcx/platform-type-class.md). Guid에는 다음과 같은 멤버도 있습니다.  
  
|멤버|설명|  
|--------|--------|  
|Guid|Guid 구조체의 새 인스턴스를 초기화합니다.|  
|연산자\=\=|Equals 연산자입니다.|  
|operator\!\=|Not equals 연산자입니다.|  
|operator\(\)|Guid를 GUID로 변환합니다.|  
  
## 설명  
 Windows 함수 [CoCreateGuid](http://msdn.microsoft.com/library/windows/desktop/ms688568\(v=vs.85\).aspx)를 사용하여 새 Platform::Guid를 생성하는 방법에 대한 예제는 [WinRT 구성 요소: GUID를 생성하는 방법](http://blogs.msdn.com/b/eternalcoding/archive/2013/03/25/winrt-component-how-to-generate-a-guid.aspx)을 참조하세요.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **메타데이터:** platform.winmd  
  
## 참고 항목  
 [Platform 네임스페이스](../cppcx/platform-namespace-c-cx.md)