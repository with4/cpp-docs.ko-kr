---
title: "식 계산기 오류 CXX0033 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "CXX0033"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0033"
  - "CXX0033"
ms.assetid: 0bd62c5b-de89-481f-9b12-88fe84805afe
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 식 계산기 오류 CXX0033
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OMF 형식 정보에 오류가 있습니다.  
  
 실행 파일은 디버깅하기 위한 유효한 OMF\(개체 모듈 형식\)가 아닙니다.  
  
 이 오류는 CAN0033과 동일합니다.  
  
### 문제 해결을 위하여 확인해 볼 수 있는 원인  
  
1.  실행 파일이 현재 버전의 Visual C\+\+와 함께 릴리스된 링커로 만들어지지 않았습니다.  LINK.exe 현재 버전을 사용하여 개체 코드를 다시 링크합니다.  
  
2.  .exe 파일이 손상되었습니다.  다시 컴파일한 다음 프로그램을 다시 링크하십시오.