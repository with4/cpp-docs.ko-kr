---
title: "Platform::NotImplementedException 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::NotImplementedException"
  - "Platform/Platform::NotImplementedException::NotImplementedException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::NotImplementedException"
ms.assetid: 6da26cc2-dde8-4aea-aa85-67aac55cf97b
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 3
---
# Platform::NotImplementedException 클래스
인터페이스 멤버가 파생된 형식으로 구현되지 않은 경우 throw됩니다.  
  
## 구문  
  
```cpp  
public ref class NotImplementedException : COMException,    IException,    IPrintable,    IEquatable  
```  
  
## 설명  
 자세한 내용은 [COMException](../cppcx/platform-comexception-class.md) 클래스를 참조하세요.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **메타데이터:** platform.winmd  
  
## 참고 항목  
 [Platform::COMException 클래스](../cppcx/platform-comexception-class.md)