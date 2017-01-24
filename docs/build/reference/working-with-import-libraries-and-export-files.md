---
title: "가져오기 라이브러리 및 내보내기 파일을 사용한 작업 | Microsoft Docs"
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
  - "파일 내보내기"
  - "가져오기 라이브러리"
  - "가져오기 라이브러리, 만들기"
  - "LIB[C++], /DEF 옵션"
  - "LIB[C++], 라이브러리 가져오기 및 파일 내보내기"
ms.assetid: d8175596-9773-4c2f-959d-b05b065a5161
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 가져오기 라이브러리 및 내보내기 파일을 사용한 작업
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

LIB를 \/DEF 옵션과 함께 사용하면 가져오기 라이브러리 및 내보내기 파일을 만들 수 있습니다.  LINK는 내보내기 파일을 사용하여 내보내기\(대개, 동적 연결 라이브러리\(DLL\)\)가 들어 있는 프로그램을 빌드하고, 가져오기 라이브러리를 사용하여 다른 프로그램의 내보내기에 대한 참조를 확인합니다.  
  
 .dll을 만들기 전에 준비 단계에서 가져오기 라이브러리를 만드는 경우 가져오기 라이브러리를 빌드할 때 전달한 것과 동일한 개체 파일 집합을 .dll을 빌드할 때도 전달해야 합니다.  
  
 대부분의 경우에는 사용자가 LIB를 사용하여 가져오기 라이브러리를 만들지 않아도 됩니다.  내보내기가 들어 있는 프로그램\(실행 파일 또는 DLL\)에 링크하면 LINK에서는 해당 내보내기에 대해 설명하는 가져오기 라이브러리를 자동으로 만듭니다.  나중에 이 내보내기를 참조하는 프로그램에 링크할 때에는 가져오기 라이브러리를 지정합니다.  
  
 하지만 DLL이 직접적으로든 간접적으로든 가져오기도 수행하는 프로그램으로 내보낼 때에는 사용자가 LIB를 사용하여 가져오기 라이브러리 중 하나를 만들어야 합니다.  LIB는 가져오기 라이브러리를 만들 때 내보내기 파일도 만듭니다.  이러한 DLL 중 하나에 링크할 때에는 내보내기 파일을 사용해야 합니다.  
  
## 참고 항목  
 [LIB 참조](../../build/reference/lib-reference.md)