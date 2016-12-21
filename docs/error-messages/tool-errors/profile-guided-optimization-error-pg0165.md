---
title: "프로필 기반 최적화 오류 PG0165 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "PG0165"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PG0165"
ms.assetid: e98122e7-ddee-4a2c-96b2-d232e4c65f3e
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 프로필 기반 최적화 오류 PG0165
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Filename.pgd'을\(를\) 읽는 중 : 'PGD 버전이 지원되지 않습니다\(버전 불일치\).'  
  
 PGD 파일은 특정 컴파일러 도구 집합과 관련된 파일입니다.  이 오류는 *Filename*.pgd에 사용한 것과 다른 컴파일러를 사용할 때 발생합니다.  이 오류는 이 컴파일러 도구 집합에서 *Filename*.pgd의 데이터를 사용하여 현재 프로그램을 최적화할 수 없다는 것을 나타냅니다.  
  
 이 문제를 해결하려면 현재 컴파일러 도구 집합을 사용하여 *Filename*.pgd를 다시 생성합니다.