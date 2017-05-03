---
title: "begin 함수 | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Windows::Foundation::Collections::begin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "begin 함수"
ms.assetid: 5a44fb33-e247-49fd-b7a1-4a5b42e9e1e4
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# begin 함수
지정된 인터페이스 매개 변수로 액세스되는 컬렉션 시작 부분을 가리키는 반복자를 반환합니다.  
  
## 구문  
  
```  
  
template <typename T>   
    ::Platform::Collections::VectorIterator<T>   
    begin(  
          IVector<T>^ v         );  
  
template <typename T>   
    ::Platform::Collections::VectorViewIterator<T>   
    begin(  
          IVectorView<T>^ v  
         );   
  
template <typename T>   
    ::Platform::Collections::InputIterator<T>   
    begin(  
          IIterable<T>^ i         );  
  
```  
  
#### 매개 변수  
 `T`  
 템플릿 형식 매개 변수입니다.  
  
 `v`  
 IVector\<T\> 또는 IVectorView\<T\> 인터페이스로 액세스되는 Vector\<T\> 또는 VectorView\<T\> 개체의 컬렉션입니다.  
  
 `i`  
 IIterable\<T\> 인터페이스로 액세스할 수 있는 임의의 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 개체 컬렉션입니다.  
  
## 반환 값  
 컬렉션의 시작 부분을 가리키는 반복기입니다.  
  
## 설명  
 처음 두 템플릿 함수는 반복기를 반환하고 세 번째 템플릿 함수는 입력 반복기를 반환합니다.  
  
 begin에 의해 반환되는 VectorIterator 개체는 VectorProxy\<T\> 형식의 요소를 저장하는 프록시 반복기입니다. 그러나 프록시 개체는 사용자 코드에 거의 표시되지 않습니다. 자세한 내용은 [컬렉션\(C\+\+\/CX\)](../cppcx/collections-c-cx.md)을 참조하세요.  
  
## 요구 사항  
 **헤더:** collection.h  
  
 **네임스페이스:** Windows::Foundation::Collections  
  
## 참고 항목  
 [Windows::Foundation::Collections 네임스페이스](../cppcx/windows-foundation-collections-namespace-c-cx.md)