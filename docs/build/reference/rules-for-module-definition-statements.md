---
title: "모듈 정의 문의 규칙 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - ".def"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "모듈 정의 파일"
  - "모듈 정의 파일, 문 구문"
ms.assetid: f65cd3a7-65d7-4d06-939f-a8b1ecd50f2d
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 모듈 정의 문의 규칙
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

.def 파일의 모든 문에는 다음과 같은 구문 규칙이 적용됩니다.  특정 문에 적용되는 다른 규칙은 각 문과 함께 설명됩니다.  
  
-   문, 특성 키워드 및 사용자 지정 식별자에 대해서는 대\/소문자가 구분됩니다.  
  
-   공백이나 세미콜론\(;\)이 포함된 긴 파일 이름은 따옴표\("\)로 묶어야 합니다.  
  
-   문 키워드를 인수와 구분하고 각 문 사이를 구분하기 위해 하나 이상의 공백, 탭 또는 줄 바꿈 문자를 사용합니다.  인수를 지정하는 콜론\(:\) 또는 등호\(\=\)의 양쪽에는 공백, 탭 또는 줄 바꿈 문자를 사용할 수 있습니다.  
  
-   **NAME** 또는 **LIBRARY** 문은 사용될 경우 다른 모든 문의 앞에 와야 합니다.  
  
-   **SECTIONS** 및 **EXPORTS** 문은 .def 파일에서 한 번 이상 나타날 수 있습니다.  각 문에는 여러 개의 사양이 있을 수 있으며 공백, 탭 또는 줄 바꿈 문자로 구분됩니다.  문 키워드는 첫 번째 사양 앞에 한 번만 나타나야 하며 각각의 추가 사양 앞에서 반복될 수 있습니다.  
  
-   여러 문에는 동일한 LINK 명령줄 옵션이 있습니다.  자세한 내용은 해당되는 LINK 옵션의 설명 부분을 참조하십시오.  
  
-   .def 파일의 주석은 각 주석줄 앞에 오는 세미콜론\(;\)으로 지정됩니다.  주석은 문과 같은 줄에 표시될 수 없지만 여러 줄로 된 문에서는 사양 사이에 표시될 수 있습니다. 여러 줄로 된 문으로는 **SECTIONS**와 **EXPORTS**가 있습니다.\)  
  
-   숫자 인수는 10진수나 16진수로 지정됩니다.  
  
-   문자열 인수가 [예약어](../../build/reference/reserved-words.md)와 일치하는 경우에는 큰따옴표\("\)로 묶어야 합니다.  
  
## 참고 항목  
 [모듈 정의\(.Def\) 파일](../../build/reference/module-definition-dot-def-files.md)   
 [Frequently Asked Questions on Building](http://msdn.microsoft.com/ko-kr/56a3bb8f-0181-4989-bab4-a07ba950ab08)