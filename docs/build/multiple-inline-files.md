---
title: "인라인 파일이 여러 개인 경우 | Microsoft Docs"
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
  - "인라인 파일, 복수 NMAKE"
  - "다중 인라인 파일"
  - "NMAKE 프로그램, 인라인 파일"
ms.assetid: 6d381dcf-0ed8-45d1-8df3-b4598d860b99
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# 인라인 파일이 여러 개인 경우
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

명령을 사용하여 하나 이상의 인라인 파일을 만들 수 있습니다.  
  
## 구문  
  
```  
  
      command << <<  
inlinetext  
<<[KEEP | NOKEEP]  
inlinetext  
<<[KEEP | NOKEEP]  
```  
  
## 설명  
 각 파일에서 구분 기호가 포함된 닫기 줄 앞에 하나 이상의 인라인 텍스트 줄을 지정합니다.  첫 번째 파일의 구분 줄 다음 줄에서 두 번째 파일의 텍스트를 시작합니다.  
  
## 참고 항목  
 [메이크파일의 인라인 파일](../build/inline-files-in-a-makefile.md)