---
title: "Platform::Delegate 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Delegate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Delegate 클래스"
ms.assetid: 82b21271-768f-4193-9ca2-be68ddfd546e
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 5
---
# Platform::Delegate 클래스
함수 개체를 나타냅니다.  
  
## 구문  
  
```cpp  
public delegate void delegate_name();  
```  
  
## 멤버  
 Delegate 클래스에는 [Platform::Object 클래스](../cppcx/platform-object-class.md)에서 파생된 Equals\(\), GetHashCode\(\) 및 ToString\(\) 메서드가 있습니다.  
  
## 설명  
 [delegate](../Topic/delegate%20%20\(C++%20Component%20Extensions\).md) 키워드를 사용하여 대리자를 만듭니다. Platform::Delegate를 명시적으로 사용하지 마세요. 자세한 내용은 [대리자](../cppcx/delegates-c-cx.md)을 참조하세요. 대리자를 만들고 사용하는 방법에 대한 예제는 [C\+\+로 Windows Runtime 구성 요소 만들기](../Topic/Creating%20Windows%20Runtime%20Components%20in%20C++.md)를 참조하세요.  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **메타데이터:** platform.winmd  
  
## 참고 항목  
 [Platform 네임스페이스](../cppcx/platform-namespace-c-cx.md)