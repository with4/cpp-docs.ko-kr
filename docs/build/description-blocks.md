---
title: "설명 블록 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "블록, 설명"
  - "설명 블록"
  - "NMAKE 프로그램, 설명 블록"
ms.assetid: 1321f228-d389-40ac-b0cd-4f6e9293602b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 설명 블록
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

설명 블록은 종속 줄이며, 그 뒤에 명령 블록이 올 수 있습니다.  
  
```  
targets... : dependents...  
    commands...  
```  
  
 종속 줄은 하나 이상의 대상과 0개 이상의 종속 파일을 지정합니다.  대상은 줄의 시작에 지정되어야 합니다.  대상과 종속 파일은 콜론\(:\)으로 구분하며 공백이나 탭을 사용할 수 있습니다.  줄을 분할하려면 대상이나 종속 파일 뒤에 백슬래시\(\\\)를 사용합니다.  대상이 없거나, 대상의 타임스탬프가 종속 파일보다 오래되었거나, 대상이 [의사 대상](../build/pseudotargets.md)인 경우 NMAKE는 명령을 실행합니다.  종속 파일이 다른 곳에 있는 대상이고, 존재하지 않거나 자신의 종속 파일에 대하여 오래된 경우, NMAKE는 종속 파일을 업데이트한 후 현재 종속 줄을 업데이트합니다.  
  
## 추가 정보  
 [대상](../build/targets.md)  
  
 [종속 파일](../build/dependents.md)  
  
## 참고 항목  
 [NMAKE 참조](../build/nmake-reference.md)