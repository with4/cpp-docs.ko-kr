---
title: "HandleT::operator= 연산자 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleT::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "operator= 연산자"
ms.assetid: 9e42dcca-30fa-4e8b-8954-802fd64a5595
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HandleT::operator= 연산자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

현재 HandleT 개체에 지정된 된 HandleT 개체의 값을 이동합니다.  
  
## 구문  
  
```  
HandleT& operator=(  
   _Inout_ HandleT&& h  
);  
```  
  
#### 매개 변수  
 `h`  
 핸들에 대한 rvalue 참조입니다.  
  
## 반환 값  
 현재 HandleT개체에 대한 참조입니다.  
  
## 설명  
 이 작업을 매개 변수에서 지정한 HandleT 개체 `h`를 무효화합니다.  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers  
  
## 참고 항목  
 [HandleT 클래스](../windows/handlet-class.md)