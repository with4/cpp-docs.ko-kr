---
title: "Box::operator Box&lt;T&gt;^ Operator | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Box::operator Box<T>^"
dev_langs: 
  - "C++"
ms.assetid: c2c89385-c334-4b09-8f87-d46ea4809232
caps.latest.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Box::operator Box&lt;T&gt;^ Operator
값 클래스 `T`를 `Box<T>`로 boxing 변환할 수 있습니다.  
  
## 구문  
  
```cpp  
operator Box<const T>^(const T valueType);  
```  
  
#### 매개 변수  
 `T`  
 모든 열거형 형식, 값 클래스 또는 값 구조체입니다.[default 네임스페이스](../cppcx/default-namespace.md)에 기본 제공 형식을 포함합니다.  
  
## 반환 값  
 ref 클래스에 boxing된 원래 값을 나타내는 `Platform::Box<T>``^` 인스턴스입니다.  
  
## 요구 사항  
 **헤더:** vccorlib.h  
  
 **네임스페이스:** Platform  
  
## 참고 항목  
 [Platform::Box 클래스](../cppcx/platform-box-class.md)   
 [Platform::IBox 인터페이스](../cppcx/platform-ibox-interface.md)   
 [boxing](../cppcx/boxing-c-cx.md)