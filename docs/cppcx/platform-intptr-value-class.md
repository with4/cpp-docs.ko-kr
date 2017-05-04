---
title: "Platform::IntPtr 값 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::IntPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::IntPtr 구조체"
ms.assetid: 6c0326e8-edfd-4e53-a963-240b845dcde8
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::IntPtr 값 클래스
플랫폼\(32비트 또는 64비트\)에 맞는 크기의 부호 있는 포인터 또는 핸들을 나타냅니다.  
  
## 구문  
  
```cpp  
public value struct IntPtr  
```  
  
## 멤버  
 IntPtr에는 다음과 같은 멤버가 있습니다.  
  
|멤버|설명|  
|--------|--------|  
|[IntPtr::IntPtr 생성자](../cppcx/intptr-intptr-constructor.md)|IntPtr의 새 인스턴스를 초기화합니다.|  
|[IntPtr::op\_explicit 연산자](../cppcx/intptr-op-explicit-operator.md)|지정된 매개 변수를 IntPtr 또는 IntPtr 값에 대한 포인터로 변환합니다.|  
|[IntPtr::ToInt32 메서드](../cppcx/intptr-toint32-method.md)|현재 IntPtr을 32비트 정수로 변환합니다.|  
  
## 요구 사항  
 **지원되는 최소 클라이언트:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **지원되는 최소 서버:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **네임스페이스:** Platform  
  
 **메타데이터:** platform.winmd  
  
## 참고 항목  
 [Platform 네임스페이스](../cppcx/platform-namespace-c-cx.md)