---
title: "메이크파일의 특수 문자 | Microsoft Docs"
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
  - "매크로, 특수 문자"
  - "메이크파일, 특수 문자"
  - "NMAKE 프로그램, 특수 문자"
  - "특수 문자, NMAKE 매크로"
ms.assetid: 92c34ab5-ca6b-4fc0-bcf4-3172eaeda9f0
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 메이크파일의 특수 문자
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

NMAKE 특수 문자를 리터럴 문자로 사용하려면 해당 문자 앞에 캐럿\(^\)을 사용합니다.  NMAKE는 다른 문자 앞에 있는 캐럿을 무시합니다.  특수 문자의 예는 다음과 같습니다.  
  
 `:  ;  #  (  )  $  ^  \  {  }  !  @  —`  
  
 따옴표 붙은 문자열 안의 캐럿\(^\)은 리터럴 캐럿 문자로 처리됩니다.  줄 끝에 캐럿이 오면 문자열이나 매크로에 리터럴 줄 바꿈 문자가 삽입됩니다.  
  
 매크로에서 줄 바꿈 문자 앞에 오는 백슬래시\(\\\)는 공백으로 바뀝니다.  
  
 명령에서 백분율 기호\(%\)는 파일 지정자입니다.  %를 문자 그대로 명령에 나타내려면 하나의 백분율 기호 대신 두 개의 백분율 기호\(%%\)를 지정합니다.  그 외의 경우에는 NMAKE가 하나의 %는 문자 그대로 해석하지만 두 개의 %%는 항상 하나의 %로 해석합니다.  그러므로 리터럴 %%를 나타내려면 세 개의 백분율 기호 %%% 또는 네 개의 백분율 기호 %%%%를 지정합니다.  
  
 명령에 달러 기호\($\)를 리터럴 문자로 사용하려면 두 개의 달러 기호\($$\)를 지정합니다.  ^$가 리터럴 $를 나타내는 경우에도 이 방법을 사용할 수 있습니다.  
  
## 참고 항목  
 [메이크파일의 내용](../build/contents-of-a-makefile.md)