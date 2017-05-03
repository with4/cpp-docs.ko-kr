---
title: "Platform::WrongThreadException 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::WrongThreadException"
  - "Platform/Platform::WrongThreadException::WrongThreadException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::WrongThreadException"
ms.assetid: c193f97e-0392-4535-a4c4-0711e4e4a836
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 5
---
# Platform::WrongThreadException 클래스
프록시 개체용 인터페이스 포인터를 통해 스레드의 아파트에 속하지 않는 스레드가 호출될 경우 throw됩니다.  
  
## 구문  
  
```cpp  
public ref class WrongThreadException : COMException,    IException,    IPrintable,    IEquatable  
```  
  
## 설명  
 자세한 내용은 [COMException](../cppcx/platform-comexception-class.md)을 참조하세요.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **메타데이터:** platform.winmd  
  
## 참고 항목  
 [Platform::COMException 클래스](../cppcx/platform-comexception-class.md)