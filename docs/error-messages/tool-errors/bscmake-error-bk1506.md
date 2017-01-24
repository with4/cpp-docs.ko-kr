---
title: "BSCMAKE 오류 BK1506 | Microsoft Docs"
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
  - "BK1506"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BK1506"
ms.assetid: f51f8cea-f8fc-4323-bcf2-b7bd119792ee
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# BSCMAKE 오류 BK1506
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'filename' 파일을 열 수 없습니다. \[: reason\]  
  
 BSCMAKE가 파일을 열 수 없습니다.  
  
### 문제 해결을 위하여 확인해 볼 수 있는 원인  
  
1.  파일이 다른 프로세스에서 잠겼습니다.  `reason` 내용이 **사용 권한이 거부되었습니다**이면 브라우저가 해당 파일을 사용 중일 수도 있습니다.  찾아보기 창을 닫고 다시 빌드하십시오.  
  
2.  디스크가 꽉 찼습니다.  
  
3.  하드웨어 오류입니다.  
  
4.  지정한 출력 파일 이름은 기존 하위 디렉터리의 이름과 동일합니다.