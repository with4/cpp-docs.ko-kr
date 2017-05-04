---
title: "Platform::ChangedStateException 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::ChangedStateException"
  - "Platform/Platform::ChangedStateException::ChangedStateException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::ChangedStateException"
ms.assetid: f894beac-9e80-4fac-ac25-89f1dbc0a6a4
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::ChangedStateException 클래스
개체의 내부 상태가 변경되어 메서드의 결과가 무효화될 때 throw됩니다.  
  
## 구문  
  
```cpp  
public ref class ChangedStateException : COMException,    IException,    IPrintable,    IEquatable  
```  
  
## 설명  
 부모 컬렉션이 변경된 후 컬렉션 반복기 또는 컬렉션 뷰의 메서드가 호출되어 메서드 결과가 무효화되는 경우가 이 예외가 throw되는 한 가지 예입니다.  
  
 자세한 내용은 [COMException](../cppcx/platform-comexception-class.md) 클래스를 참조하세요.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **메타데이터:** platform.winmd  
  
## 참고 항목  
 [Platform::COMException 클래스](../cppcx/platform-comexception-class.md)