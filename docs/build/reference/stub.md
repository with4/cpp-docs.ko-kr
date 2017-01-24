---
title: "STUB | Microsoft Docs"
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
  - "STUB"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "STUB .def 파일 문"
ms.assetid: 0a3b9643-19ed-47e9-8173-ee16bc8ed056
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# STUB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

가상 장치 드라이버\(VxD\)를 빌드하는 모듈 정의 파일에 STUB을 사용하면 IMAGE\_DOS\_HEADER 구조체\(WINNT.H에서 정의\)가 들어 있는 파일 이름이 기본 헤더 대신 가상 장치 드라이버\(VxD\)에서 사용되도록 지정할 수 있습니다.  
  
```  
STUB:filename  
```  
  
## 설명  
 이와 동일한 *filename* 지정 방법은 링커 옵션 [\/STUB](../../build/reference/stub-ms-dos-stub-file-name.md)을 사용하는 것입니다.  
  
 STUB은 VxD를 빌드할 때만 모듈 정의 파일에서 유효합니다.  
  
## 참고 항목  
 [모듈 정의 문의 규칙](../../build/reference/rules-for-module-definition-statements.md)