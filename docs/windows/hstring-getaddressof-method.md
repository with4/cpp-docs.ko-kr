---
title: "HString::GetAddressOf 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HString::GetAddressOf"
dev_langs: 
  - "C++"
ms.assetid: 6050decf-5f99-49f0-9497-1c8192c485ae
caps.latest.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 2
---
# HString::GetAddressOf 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

기본 HSTRING 핸들에 대한 포인터를 검색합니다.  
  
## 구문  
  
```  
HSTRING* GetAddressOf() throw()  
```  
  
## 반환 값  
 기본 HSTRING 핸들에 대한 포인터를 검색합니다.  
  
## 설명  
 이 작업이 끝나면 내부 HSTRING 핸들의 문자열 값이 소멸됩니다.  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers  
  
## 참고 항목  
 [HString 클래스](../windows/hstring-class.md)