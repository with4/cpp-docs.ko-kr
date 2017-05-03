---
title: "Platform::ValueType 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "02/03/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::ValueType"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::ValueType 클래스"
ms.assetid: 79aa8754-b140-4974-a5b1-be046938a10a
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 2
---
# Platform::ValueType 클래스
값 형식 인스턴스의 기본 클래스입니다.  
  
## 구문  
  
```cpp  
public ref class ValueType : Object  
```  
  
## 설명  
 ValueType 클래스는 값 형식을 생성하는 데 사용됩니다. ValueType은 기본 멤버인 Object에서 파생됩니다. 그러나 컴파일러는 해당 기본 멤버를 ValueType 클래스에서 파생된 값 형식에서 분리합니다. 컴파일러는 값 형식이 boxing될 때 해당 기본 멤버를 다시 연결합니다.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **메타데이터:** platform.winmd  
  
## 참고 항목  
 [Platform 네임스페이스](../cppcx/platform-namespace-c-cx.md)