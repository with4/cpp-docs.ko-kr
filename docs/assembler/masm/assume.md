---
title: "ASSUME | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ASSUME"
  - "_assume_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ASSUME directive"
ms.assetid: cd162070-aee9-4c65-babc-005c6cc73d7c
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ASSUME
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

레지스터 값은 오류 수 있습니다.  
  
## 구문  
  
```  
  
      ASSUME segregister:name [[, segregister:name]]...  
ASSUME dataregister:type [[, dataregister:type]]...  
ASSUME register:ERROR [[, register:ERROR]]...  
ASSUME [[register:]] NOTHING [[, register:NOTHING]]...  
```  
  
## 설명  
 후에 `ASSUME` , 어셈블러를 감시 하는 지정 된 레지스터의 값에 대 한 변경 관리를입니다.  **오류** 레지스터를 사용 하는 경우 오류가 발생 합니다.  **아무것도** 제거 등록 오류를 검사 합니다.  다양 한 종류의 가정에 문 결합할 수 있습니다.  
  
## 참고 항목  
 [Directives Reference](../../assembler/masm/directives-reference.md)