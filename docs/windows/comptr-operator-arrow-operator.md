---
title: "ComPtr::operator-&gt; 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::ComPtr::operator->"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator-> 연산자"
ms.assetid: 7b7faefd-d1e4-4f31-a77d-17a42e0d6b6a
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::operator-&gt; 연산자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

현재 템플릿 매개 변수로 지정된 형식에 대한 포인터를 검색합니다.  
  
## 구문  
  
```  
WRL_NOTHROW Microsoft::WRL::Details::RemoveIUnknown<InterfaceType>* operator->() const;  
```  
  
## 반환 값  
 현재 서식 파일 형식 이름으로 지정된 형식에 대한 포인터입니다.  
  
## 설명  
 이 도우미 함수 STDMETHOD 매크로 사용하여 발생하는 불필요한 오버 헤드를 제거합니다.  이 함수는 IUnknown 형식을 virtual 대신 private으로 만듭니다.  
  
## 요구 사항  
 **헤더:** client.h  
  
 **네임스페이스:** Microsoft::WRL  
  
## 참고 항목  
 [ComPtr 클래스](../windows/comptr-class.md)