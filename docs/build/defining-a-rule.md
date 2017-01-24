---
title: "규칙 정의 | Microsoft Docs"
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
  - "유추 규칙 정의"
  - "NMAKE 프로그램, 유추 규칙"
ms.assetid: 071cd092-3f2e-4065-b0fb-36a9d393cfa8
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 규칙 정의
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

*fromext*는 종속 파일의 확장명을 나타내고 *toext*는 대상 파일의 확장명을 나타냅니다.  
  
```  
.fromext.toext:  
   commands  
```  
  
## 설명  
 확장명은 대\/소문자를 구분하지 않습니다.  매크로를 호출하여 *fromext*와 *toext*를 나타낼 수 있습니다. 매크로는 전처리 중에 확장됩니다.  줄의 시작에서 *fromext* 앞에 마침표\(.\)를 표시해야 합니다.  콜론\(:\) 뒤에는 0개 이상의 공백이나 탭이 옵니다.  콜론 뒤에는 공백이나 탭만 올 수 있으며 명령을 지정하려면 세미콜론\(;\)을 사용하고 주석이나 줄 바꿈 문자를 지정하려면 숫자 기호\(\#\)를 사용합니다.  그 외에는 공백을 사용할 수 없습니다.  명령은 설명 블록과 같은 내용으로 지정됩니다.  
  
## 추가 정보  
 [규칙에서 경로 검색](../build/search-paths-in-rules.md)  
  
## 참고 항목  
 [유추 규칙](../build/inference-rules.md)