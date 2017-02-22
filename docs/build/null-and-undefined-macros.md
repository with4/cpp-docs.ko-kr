---
title: "null 및 정의되지 않은 매크로 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "매크로, null 및 정의되지 않음"
  - "NMAKE 프로그램, null 매크로"
  - "NMAKE 프로그램, 정의되지 않은 매크로"
  - "NMAKE의 Null 매크로"
  - "정의되지 않은 매크로 및 NMAKE"
ms.assetid: 1db4611a-1755-4328-b00f-d35365af8b6c
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# null 및 정의되지 않은 매크로
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

null 및 정의되지 않은 매크로는 모두 null 문자열로 확장되지만 null 문자열로 정의된 매크로는 전처리 식에 정의된 것으로 간주합니다.  매크로를 null 문자열로 정의하려면 명령줄이나 명령 파일에서 등호\(\=\) 뒤에 공백이나 탭만 지정하고 null 문자열이나 정의를 큰따옴표\(" "\)로 묶습니다.  매크로를 정의하지 않으려면 **\!UNDEF**를 사용합니다. 자세한 내용은 [메이크파일 전처리 지시문](../build/makefile-preprocessing-directives.md)을 참조하십시오.  
  
## 참고 항목  
 [NMake 매크로 정의](../build/defining-an-nmake-macro.md)