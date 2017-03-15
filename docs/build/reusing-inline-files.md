---
title: "인라인 파일 다시 사용 | Microsoft Docs"
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
  - "인라인 파일, NMAKE 다시 사용"
  - "NMAKE 프로그램, 인라인 파일"
  - "인라인 파일 다시 사용"
ms.assetid: d42dbffb-2cef-4ccb-9a1f-20b8ef81481c
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 인라인 파일 다시 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

인라인 파일을 다시 사용하려면 파일을 정의하고 첫 번째로 사용한 위치에 \<\<\<\<*filename*을 지정한 다음, 같은 명령이나 다른 명령에 \<\< 없이 *filename*을 다시 사용합니다.  인라인 파일을 사용하는 모든 명령을 실행하기 전에 인라인 파일을 만들 명령을 실행해야 합니다.  
  
## 참고 항목  
 [메이크파일의 인라인 파일](../build/inline-files-in-a-makefile.md)