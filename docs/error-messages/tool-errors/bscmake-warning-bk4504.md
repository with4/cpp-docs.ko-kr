---
title: "BSCMAKE 경고 BK4504 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "BK4504"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BK4504"
ms.assetid: b56ee2d4-ad44-40f4-98c0-75934ea44a6c
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# BSCMAKE 경고 BK4504
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

파일에 참조가 너무 많습니다. 이 소스에서 추가 참조를 무시합니다.  
  
 .Cpp 파일에 기호 참조가 64000 개 이상 포함 되어 있습니다.  BSCMAKE는 파일에 대 한 참조가 64000가 나타나면 모든 추가 참조를 무시 합니다.  
  
 이 문제를 해결 하려면 파일을 두 개로 분할 하거나 더 64000 보다 자세한 파일 참조 기호 또는 사용의  `#pragma component(browser)`  특정 참조를 생성 하는 제한 기호를 전처리기 지시문입니다.  자세한 내용은 [구성 요소](../../preprocessor/component.md)을 참조하십시오.