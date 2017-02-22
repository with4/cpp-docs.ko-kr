---
title: "/LINENUMBERS | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/linenumbers"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/LINENUMBERS dumpbin 옵션"
  - "줄 번호"
  - "LINENUMBERS dumpbin 옵션"
  - "-LINENUMBERS dumpbin 옵션"
ms.assetid: 1681d582-2c2f-484e-9920-109959549055
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /LINENUMBERS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/LINENUMBERS  
```  
  
## 설명  
 이 옵션은 COFF 줄 번호를 표시합니다.  프로그램 데이터베이스\(\/Zi\), C7 호환\(\/Z7\) 또는 줄 번호만\(\/Zd\)으로 컴파일된 개체 파일에는 줄 번호가 있습니다.  디버그 정보 생성\(\/DEBUG\)으로 링크된 실행 파일 또는 DLL에는 COFF 줄 번호가 있습니다.  
  
 [\/HEADERS](../../build/reference/headers.md) DUMPBIN 옵션은 [\/GL](../../build/reference/gl-whole-program-optimization.md) 컴파일러 옵션으로 만든 파일에만 사용할 수 있습니다.  
  
## 참고 항목  
 [DUMPBIN 옵션](../../build/reference/dumpbin-options.md)