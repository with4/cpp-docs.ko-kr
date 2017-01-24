---
title: "HANDLETraits::Close 메서드 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::Close"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Close 메서드"
ms.assetid: 3c631a7c-ccce-472a-b1da-aab8fa815c13
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HANDLETraits::Close 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

지정된  핸들을 닫습니다.  
  
## 구문  
  
```  
inline static bool Close(  
   _In_ Type h  
);  
```  
  
#### 매개 변수  
 `h`  
 핸들을 닫습니다.  
  
## 반환 값  
 만일 핸드 `h` 가 성공적으로 닫혔다면 **true**, 그렇지 않으면 **false**  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스**Microsoft::WRL::Wrappers::HandleTraits  
  
## 참고 항목  
 [HANDLETraits 구조체](../windows/handletraits-structure.md)