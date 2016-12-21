---
title: "HandleT::Close 메서드 | Microsoft Docs"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HandleT::Close"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Close 메서드"
ms.assetid: 1b9d597c-abcf-4028-a068-0344560009f6
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# HandleT::Close 메서드
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

현재 HandleT 개체를 닫습니다.  
  
## 구문  
  
```  
void Close();  
```  
  
## 설명  
 현재 HandleT의 기반이 되는 핸들 닫히고 HandleT는 유효 하지 않은 상태로 설정 됩니다.  
  
 핸들을 제대로 닫히지 않습니다, 경우 호출 스레드에서 예외가 발생 합니다.  
  
## 요구 사항  
 **헤더:** corewrappers.h  
  
 **네임스페이스:** Microsoft::WRL::Wrappers  
  
## 참고 항목  
 [HandleT 클래스](../windows/handlet-class.md)