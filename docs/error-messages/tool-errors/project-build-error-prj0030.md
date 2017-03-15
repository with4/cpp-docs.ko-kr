---
title: "프로젝트 빌드 오류 PRJ0030 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PRJ0030"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0030"
ms.assetid: c48b3727-e166-46e7-bcd7-3e5b2ac5c1d4
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 프로젝트 빌드 오류 PRJ0030
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

매크로 확장 오류입니다.$\(macro\)에 대해 수준 32를 넘는 재귀 호출을 실행합니다.  
  
 이 오류는 매크로의 재귀 호출 때문에 발생합니다.  예를 들어, **중간 디렉터리** 속성\([일반 속성 페이지\(프로젝트\)](../../ide/general-property-page-project.md) 참조\)을 $\(IntDir\)로 설정한 경우, 재귀 호출이 발생합니다.  
  
 이 오류를 해결하려면 매크로나 속성이 사용되어 정의한 매크로에 대해 이들 매크로나 속성을 정의하지 마십시오.