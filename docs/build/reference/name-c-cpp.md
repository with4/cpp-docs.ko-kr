---
title: "NAME(C/C++) | Microsoft Docs"
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
  - "name"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "NAME .def 파일 문"
ms.assetid: 5c9b6bd8-9275-46a5-afba-f17a5936dc26
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# NAME(C/C++)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

주 출력 파일의 이름을 지정합니다.  
  
```  
NAME [application][BASE=address]  
```  
  
## 설명  
 이와 동일한 출력 파일 지정 방법은 링커 옵션 [\/OUT](../../build/reference/out-output-file-name.md)을 사용하는 것이고 이와 동일한 기준 주소 설정 방법은 링커 옵션 [\/BASE](../../build/reference/base-base-address.md)를 사용하는 것입니다.  두 옵션이 모두 지정된 경우에는 \/OUT이 **NAME**을 재정의합니다.  
  
 DLL을 빌드하는 경우 NAME은 DLL 이름에만 영향을 줍니다.  
  
## 참고 항목  
 [모듈 정의 문의 규칙](../../build/reference/rules-for-module-definition-statements.md)