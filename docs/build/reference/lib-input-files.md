---
title: "LIB 입력 파일 | Microsoft Docs"
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
  - "입력 파일, LIB"
ms.assetid: e1236f0d-cd90-446b-b900-f311f456085c
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# LIB 입력 파일
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

LIB에서 필요로 하는 입력 파일은 다음 표에서처럼 해당 LIB가 사용되고 있는 모드에 따라 다릅니다.  
  
|모드|입력|  
|--------|--------|  
|기본값\(라이브러리 빌드 또는 수정\)|COFF 개체\(.obj\) 파일, COFF 라이브러리\(.lib\), 32비트 OMF\(개체 모델 형식\) 개체\(.obj\) 파일|  
|\/EXTRACT를 사용하여 멤버 추출|COFF 라이브러리\(.lib\)|  
|\/DEF를 사용하여 내보내기 파일 및 가져오기 라이브러리 빌드|모듈 정의\(.def\) 파일, COFF 개체\(.obj\) 파일, COFF 라이브러리\(.lib\), 32비트 OMF 개체\(.obj\) 파일|  
  
> [!NOTE]
>  16비트 버전의 LIB에서 만들어진 OMF 라이브러리는 32비트 버전의 LIB에 대한 입력 파일로 사용할 수 없습니다.  
  
## 참고 항목  
 [LIB 개요](../../build/reference/overview-of-lib.md)