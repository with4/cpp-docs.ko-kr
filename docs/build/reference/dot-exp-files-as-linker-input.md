---
title: "링커 입력 파일로 사용하는 .Exp 파일 | Microsoft Docs"
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
  - ".exp 파일[C++]"
  - "EXP 파일"
  - "데이터 내보내기, 내보내기(.exp) 파일"
  - "함수 내보내기"
  - "함수 내보내기, 내보낸 함수 정보"
  - "함수[C++], 내보내기"
  - "가져오기 라이브러리, 링커 파일"
  - "링크[C++], 내보내기"
ms.assetid: 399f5636-0a4d-462e-b500-5f5b9ae5ad22
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 링커 입력 파일로 사용하는 .Exp 파일
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

내보내기 파일\(.exp\)에는 내보낸 함수와 데이터 항목에 대한 정보가 들어 있습니다.  LIB에서는 내보내기 라이브러리를 만들 때 .exp 파일도 만듭니다.  다른 프로그램으로 내보내기도 하고 가져오기도 하는 프로그램을 직접 또는 간접적으로 링크할 때 이 .exp 파일을 사용합니다.  .exp 파일을 사용하여 링크하면 LINK에서는 가져오기 라이브러리를 이미 만들었다고 가정하기 때문에 다시 만들지 않습니다.  .exp 파일과 가져오기 라이브러리에 대한 자세한 내용은 [가져오기 라이브러리 및 내보내기 파일을 사용한 작업](../../build/reference/working-with-import-libraries-and-export-files.md)을 참조하십시오.  
  
## 참고 항목  
 [LINK 입력 파일](../../build/reference/link-input-files.md)   
 [링커 옵션](../../build/reference/linker-options.md)