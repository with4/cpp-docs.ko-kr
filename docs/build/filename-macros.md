---
title: "파일 이름 매크로 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "NMAKE의 파일 이름 매크로"
  - "매크로, NMAKE"
  - "NMAKE 프로그램, 파일 이름 매크로"
ms.assetid: 20afd6b3-5b6c-4e33-9d01-309ce98ef9db
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 파일 이름 매크로
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

파일 이름 매크로는 종속 줄에 지정된 파일 이름으로 미리 정의됩니다\(디스크의 전체 파일 이름 사양이 아님\).  이 매크로는 호출될 때 괄호로 묶을 필요가 없으므로 다음과 같이 $만 지정합니다.  
  
|매크로|의미|  
|---------|--------|  
|**$@**|현재 지정된 현재 대상의 전체 이름\(경로, 기본 이름, 확장명\)입니다.|  
|**$$@**|현재 지정된 현재 대상의 전체 이름\(경로, 기본 이름, 확장명\)입니다.  종속 줄의 종속 파일로만 유효합니다.|  
|**$\***|파일 확장명을 제외한 현재 대상의 경로와 기본 이름입니다.|  
|**$\*\***|현재 대상의 모든 종속 파일입니다.|  
|**$?**|타임스탬프가 현재 대상 이후인 모든 종속 파일입니다.|  
|**$\<**|타임스탬프가 현재 대상 이후인 종속 파일입니다.  유추 규칙의 명령에만 유효합니다.|  
  
 미리 정의된 파일 이름 매크로의 일부만 지정하려면 매크로 한정자를 추가하고 수정된 매크로를 괄호로 묶습니다.  
  
|한정자|수정된 파일 이름 부분|  
|---------|------------------|  
|**D**|드라이브와 디렉터리|  
|**B**|기본 이름|  
|**F**|기본 이름과 확장명|  
|**R**|드라이브, 기본 이름 및 확장명|  
  
## 참고 항목  
 [특수 NMake 매크로](../build/special-nmake-macros.md)