---
title: "back_inserter 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Windows::Foundation::Collections::back_inserter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "back_inserter 함수"
ms.assetid: 91476338-5548-44b7-bc7e-2150f4fbe31a
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# back_inserter 함수
지정된 컬렉션 끝에 요소를 삽입하는 데 사용되는 반복기를 반환합니다.  
  
## 구문  
  
```  
  
template <  
   typename T  
   >  
   ::Platform::BackInsertIterator<T>   
    back_inserter(  
                  IVector<T>^ v  
                 );  
  
template <  
   typename T  
   >  
   ::Platform::BackInsertIterator<T>   
   back_inserter(  
                IObservableVector<T>^ v  
                );  
```  
  
#### 매개 변수  
 `T`  
 템플릿 형식 매개 변수입니다.  
  
 `v`  
 내부 컬렉션에 대한 액세스를 제공하는 인터페이스 포인터입니다.  
  
## 반환 값  
 반복기입니다.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Windows::Foundation::Collections  
  
## 참고 항목  
 [Windows::Foundation::Collections 네임스페이스](../cppcx/windows-foundation-collections-namespace-c-cx.md)