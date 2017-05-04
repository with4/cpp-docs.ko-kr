---
title: "WeakReference::Resolve 메서드(Platform 네임스페이스) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/WeakReference::Resolve"
ms.assetid: 78bbcadd-89d0-4863-a4e8-1d84040eed7d
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# WeakReference::Resolve 메서드(Platform 네임스페이스)
원래 ref 클래스에 대한 핸들 또는 `nullptr`\(개체가 더 이상 존재하지 않는 경우\)을 반환합니다.  
  
## 구문  
  
```vb  
  
template<typename T>  
T^ Resolve() const  
```  
  
#### 매개 변수  
  
## 속성 값\/반환 값  
 WeakReference 개체가 이전에 연결되었던 ref 클래스에 대한 핸들 또는 nullptr입니다.  
  
## 설명  
  
## 예제  
 코드 예제에 대한 설명입니다.  
  
```  
  
Bar^ bar = ref new Bar(); //use bar... if (bar != nullptr) { WeakReference wr(bar); Bar^ newReference = wr.Resolve<Bar>(); }  
```  
  
 형식 매개 변수는 T^이 아니라 T입니다.  
  
## 참고 항목  
 [Platform 네임스페이스](../cppcx/platform-namespace-c-cx.md)