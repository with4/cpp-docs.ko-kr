---
title: "전처리에서 프로그램 실행 | Microsoft Docs"
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
  - "프로그램 실행[C++]"
ms.assetid: 5ecf123a-20e5-40cd-b8d8-dd5a9fdd4b24
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 전처리에서 프로그램 실행
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

전처리 중에 명령의 종료 코드를 사용하려면 대괄호\(\[ \]\) 안에 인수를 사용하여 명령을 지정합니다.  모든 매크로는 명령이 실행되기 전에 확장됩니다.  NMAKE가 명령 사양을 명령의 종료 코드로 바꾸면 전처리를 제어하는 식에 이 종료 코드를 사용할 수 있습니다.  
  
## 참고 항목  
 [메이크파일 전처리 식](../build/expressions-in-makefile-preprocessing.md)