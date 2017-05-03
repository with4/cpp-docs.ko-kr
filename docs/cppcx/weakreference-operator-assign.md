---
title: "WeakReference::operator= | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/WeakReference::operator="
ms.assetid: 20b034d1-8f4f-46ae-81f0-73b76599f86b
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# WeakReference::operator=
WeakReference에 값을 할당합니다.  
  
## 구문  
  
```cpp  
WeakReference& operator=(decltype(__nullptr));  
  
WeakReference& operator=(const WeakReference& __otherArg);  
  
WeakReference& operator=(WeakReference&& __otherArg);  
  
WeakReference& operator=(const volatile ::Platform::Object^ const __otherArg);  
  
```  
  
## 설명  
 위의 목록에서 마지막 오버로드를 사용하면 WeakReference 변수에 ref 클래스를 할당할 수 있습니다. 이 경우 ref 클래스가 [Platform::Object](../cppcx/platform-object-class.md)^으로 다운캐스팅됩니다.[WeakReference::Resolve\<T\>](../cppcx/weakreference-resolve-method-platform-namespace.md) 멤버 함수에서 형식 매개 변수에 대한 인수로 지정하여 나중에 원래 형식을 복원합니다.  
  
## 요구 사항  
 Windows 8.0 이상  
  
## 참고 항목  
 [Platform::WeakReference 클래스](../cppcx/platform-weakreference-class.md)