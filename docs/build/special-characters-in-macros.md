---
title: "매크로의 특수 문자 | Microsoft Docs"
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
  - "특수 문자, NMAKE 매크로"
ms.assetid: c0a06cfc-7103-4ee2-a585-e8f6e85dccd7
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 매크로의 특수 문자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

정의 뒤에 오는 숫자 기호\(\#\)는 주석을 지정합니다.  매크로에 리터럴 숫자 기호를 지정하려면 ^\#와 같이 캐럿\(^\)을 숫자 기호 앞에 사용합니다.  
  
 달러 기호\($\)는 매크로 호출을 지정합니다.  리터럴 $를 지정하려면 $$를 사용합니다.  
  
 정의를 다음 줄까지 확장하려면 줄 끝에 백슬래시\(\\\)를 입력합니다.  매크로가 호출되면 백슬래시와 줄 바꿈 문자를 공백으로 바꿉니다.  줄 끝에 리터럴 백슬래시를 지정하려면 백슬래시 앞에 캐럿\(^\)을 사용하거나 뒤에 주석 지정자\(\#\)를 사용합니다.  
  
 리터럴 줄 바꿈 문자를 지정하려면 다음과 같이 줄 끝에 캐럿\(^\)을 사용합니다.  
  
```  
CMDS = cls^  
dir  
```  
  
## 참고 항목  
 [NMake 매크로 정의](../build/defining-an-nmake-macro.md)