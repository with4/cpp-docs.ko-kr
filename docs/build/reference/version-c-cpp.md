---
title: "VERSION(C/C++) | Microsoft Docs"
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
  - "VERSION"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VERSION .def 파일 문"
ms.assetid: 3533b97c-5183-45f9-9ca8-4e63462b5d26
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# VERSION(C/C++)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

LINK에서 .exe 파일 또는 DLL의 헤더에 버전 번호를 지정하도록 지시합니다.  
  
```  
VERSION major[.minor]  
```  
  
## 설명  
 *major* 및 *minor* 인수는 0에서 65,535까지의 10진수로서,  기본값은 버전 0.0입니다.  
  
 이와 동일한 버전 번호 지정 방법은 [버전 정보](../../build/reference/version-version-information.md)\(\/VERSION\) 옵션을 사용하는 것입니다.  
  
## 참고 항목  
 [모듈 정의 문의 규칙](../../build/reference/rules-for-module-definition-statements.md)