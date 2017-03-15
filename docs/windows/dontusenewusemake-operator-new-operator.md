---
title: "DontUseNewUseMake::operator 새 연산자 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::DontUseNewUseMake::operator new"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator new 연산자"
ms.assetid: 6af07a0d-2271-430c-9d9b-5a4223fed049
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# DontUseNewUseMake::operator 새 연산자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## 구문  
  
```  
void* operator new(  
   size_t,  
   _In_ void* placement  
);  
```  
  
#### 매개 변수  
 `__unnamed0`  
 할당할 메모리의 바이트 수를 지정 하는 명명 되지 않은 매개 변수입니다.  
  
 `placement`  
 할당 형식입니다.  
  
## 반환 값  
 만일 연산자 `new`를 오버로드할 경우, 추가적인 인수를 전달할 방법을 제공합니다.  
  
## 설명  
 연산자 `new` 를 오버로드하고 RuntimeClass에서 사용되는 것을 막습니다.  
  
## 요구 사항  
 **헤더:** implements.h  
  
 **네임스페이스**Microsoft::WRL::Details  
  
## 참고 항목  
 [DontUseNewUseMake 클래스](../windows/dontusenewusemake-class.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)