---
title: "링커 도구 오류 LNK1106 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1106"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1106"
ms.assetid: 528f7e65-04be-4966-b8af-9276837c7cda
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 도구 오류 LNK1106
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

파일이 잘못되었거나 디스크가 꽉 찼습니다. location을\(를\) 찾을 수 없습니다.  
  
 도구가 메모리 매핑된 파일에서 `location`을 읽거나 쓰지 못했습니다.  
  
### 문제 해결을 위하여 확인해 볼 수 있는 원인  
  
1.  디스크가 꽉 찼습니다.  
  
     디스크 공간을 늘리고 다시 링크하십시오.  
  
2.  네트워크를 통해 링크하려고 했습니다.  
  
     몇몇 네트워크에서는 링커가 사용하는 메모리 매핑된 파일을 완전하게 지원하지 않습니다.  로컬 디스크에서 링크해 보십시오.  
  
3.  디스크에 잘못된 블록이 있습니다.  
  
     운영 체제와 디스크 하드웨어에서 이러한 오류가 발생해도 디스크 검사 프로그램을 실행할 수 있습니다.  
  
4.  힙 공간이 부족합니다.  
  
     자세한 내용은 [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md)을 참조하십시오.