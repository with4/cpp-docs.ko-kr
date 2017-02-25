---
title: "LIB 출력 파일 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Lib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "출력 파일, LIB"
ms.assetid: e73d2f9b-a42d-402b-b7e3-3a94bebb317e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# LIB 출력 파일
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

LIB에서 생성되는 출력 파일은 다음 표에서처럼 해당 LIB가 사용되고 있는 모드에 따라 다릅니다.  
  
|모드|Output|  
|--------|------------|  
|기본값\(라이브러리 빌드 또는 수정\)|COFF 라이브러리\(.lib\)|  
|\/EXTRACT를 사용하여 멤버 추출|개체\(.obj\) 파일|  
|\/DEF를 사용하여 내보내기 파일 및 가져오기 라이브러리 빌드|가져오기 라이브러리\(.lib\) 및 내보내기\(.exp\) 파일|  
  
## 참고 항목  
 [LIB 개요](../../build/reference/overview-of-lib.md)