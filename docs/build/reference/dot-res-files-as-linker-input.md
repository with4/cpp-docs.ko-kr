---
title: "링커 입력 파일로 사용하는 .Res 파일 | Microsoft Docs"
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
  - "링커 입력 파일로 사용하는 .res 파일"
  - "링크[C++], 리소스 파일"
  - "링커 입력으로 사용하는 RES 파일"
  - "리소스 파일, 링크"
ms.assetid: 9c37ab00-97df-4d9a-91cd-6bf132970683
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 입력 파일로 사용하는 .Res 파일
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

프로그램을 링크할 때 .res 파일을 지정할 수 있습니다.  .res 파일은 RC\(리소스 컴파일러\)에서 만듭니다.  LINK에서는 .res 파일을 자동으로 COFF로 변환합니다.  CVTRES.exe 도구는 LINK.exe가 있는 디렉터리나 PATH 환경 변수로 지정된 디렉터리에 있어야 합니다.  
  
## 참고 항목  
 [LINK 입력 파일](../../build/reference/link-input-files.md)   
 [링커 옵션](../../build/reference/linker-options.md)