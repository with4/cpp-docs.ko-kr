---
title: "기타 LIB 출력 | Microsoft Docs"
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
  - "Lib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "출력 파일, LIB"
ms.assetid: 656864a6-0b7a-4633-8dc6-ee3b1766d836
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 기타 LIB 출력
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

기본 모드에서는 \/LIST 옵션을 사용하여 결과 라이브러리에 대한 정보를 표시할 수 있습니다.  이렇게 출력된 내용을 파일로 리디렉션할 수 있습니다.  
  
 LIB는 \/NOLOGO 옵션이 사용되지 않은 경우 저작권 및 버전 관련 메시지를 표시하고 명령 파일을 에코합니다.  
  
 다른 입력 내용 없이 `lib`만을 입력할 경우 LIB는 해당 옵션을 요약한 사용법 문을 표시합니다.  
  
 LIB에서 표시하는 오류 및 경고 메시지의 형식은 LNK*nnnn*입니다.  LINK, DUMPBIN 및 EDITBIN 도구도 이 범위의 오류를 사용합니다.  출력 창에서 해당 오류를 선택하고 F1 키를 누르면 도움말을 볼 수 있습니다.  
  
## 참고 항목  
 [LIB 개요](../../build/reference/overview-of-lib.md)