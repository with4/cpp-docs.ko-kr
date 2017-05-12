---
title: "Platform::WeakReference 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform::WeakReference"
ms.assetid: 8cfe1977-a8c7-4b7b-b539-25c77ed4c5f1
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::WeakReference 클래스
ref 클래스 인스턴스에 대한 약한 참조를 나타냅니다.  
  
## 구문  
  
```vb  
class WeakReference  
```  
  
#### 매개 변수  
  
## 멤버  
  
### 생성자  
  
|멤버|설명|  
|--------|--------|  
|[WeakReference::WeakReference 생성자](../cppcx/weakreference-weakreference-constructor-c-cx.md)|WeakReference 클래스의 새 인스턴스를 초기화합니다.|  
  
### 메서드  
  
|멤버|설명|  
|--------|--------|  
|[WeakReference::Resolve 메서드](../cppcx/weakreference-resolve-method-platform-namespace.md)|기본 ref 클래스에 대한 핸들 또는 nullptr\(개체가 더 이상 존재하지 않는 경우\)을 반환합니다.|  
  
### 연산자  
  
|멤버|설명|  
|--------|--------|  
|[WeakReference::operator\=](../cppcx/weakreference-operator-assign.md)|WeakReference 개체에 새 값을 할당합니다.|  
  
## 설명  
 WeakReference 클래스 자체는 ref 클래스가 아니므로 Platform::Object^에서 상속하지 않으며 public 메서드의 시그니처에 사용될 수 없습니다.  
  
## 참고 항목  
 [Platform 네임스페이스](../cppcx/platform-namespace-c-cx.md)