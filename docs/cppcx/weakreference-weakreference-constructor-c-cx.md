---
title: "WeakReference::WeakReference 생성자(C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/WeakReference::WeakReference"
ms.assetid: b2f712e0-3ee0-4a05-b861-973b4a212609
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# WeakReference::WeakReference 생성자(C++/CX)
WeakReference를 생성하는 다양한 방법을 제공합니다.  
  
## 구문  
  
```scr  
WeakReference();  
WeakReference(decltype(__nullptr));  
WeakReference(const WeakReference& __otherArg);  
WeakReference(WeakReference&& __otherArg);  
explicit WeakReference(const volatile ::Platform::Object^ const __otherArg);  
```  
  
## 예제  
  
```scr  
  
MyClass^ mc = ref new MyClass(); WeakReference wr(mc); MyClass^ copy2 = wr.Resolve<MyClass>();  
  
```  
  
## 설명  
  
## 요구 사항  
  
## 참고 항목  
 [Platform 네임스페이스](../cppcx/platform-namespace-c-cx.md)   
 [Platform::WeakReference 클래스](../cppcx/platform-weakreference-class.md)