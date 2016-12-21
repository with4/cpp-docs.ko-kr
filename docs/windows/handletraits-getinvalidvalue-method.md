---
title: "HANDLETraits::GetInvalidValue 메서드 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::GetInvalidValue"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetInvalidValue 메서드"
ms.assetid: e95d2cc1-e70f-463f-8ff0-183cdeac1138
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HANDLETraits::GetInvalidValue 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

잘못된 핸들을 나타냅니다.  
  
## 구문  
  
```  
inline static HANDLE GetInvalidValue();  
```  
  
## 반환 값  
 항상 INVALID\_HANDLE\_VALUE을 반환합니다. \(INVALID\_HANDLE\_VALUE는 Windows에 의해 정의 됩니다.\)  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers::HandleTraits  
  
## 참고 항목  
 [HANDLETraits 구조체](../windows/handletraits-structure.md)