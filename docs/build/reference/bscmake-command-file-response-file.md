---
title: "BSCMAKE 명령 파일(지시 파일) | Microsoft Docs"
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
  - "BSCMAKE, 명령 파일"
  - "BSCMAKE, 지시 파일"
  - "명령 파일"
  - "명령 파일, BSCMAKE"
  - "지시 파일"
  - "지시 파일, BSCMAKE"
ms.assetid: abdffeea-35c7-4f2d-8c17-7d0d80bac314
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# BSCMAKE 명령 파일(지시 파일)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

명령 파일에 명령줄 입력의 일부 또는 전체를 제공할 수 있습니다.  다음 구문을 사용하여 명령 파일을 지정합니다.  
  
```  
BSCMAKE @filename  
```  
  
 명령 파일은 하나만 사용할 수 있습니다.  *filename*에 경로를 지정할 수 있으며  *filename* 앞에 @ 기호가 붙습니다.  BSCMAKE는 확장명을 가정하지 않습니다.  명령줄에서 *filename* 뒤에 *sbrfiles*를 추가로 지정할 수 있습니다.  명령 파일은 명령줄에 지정하는 것과 같은 순서로 BSCMAKE에 대한 입력 내용을 포함하는 텍스트 파일입니다.  명령줄 인수는 하나 이상의 공백, 탭 또는 줄 바꿈 문자를 사용하여 구분합니다.  
  
 다음 명령은 명령 파일을 사용하여 BSCMAKE를 호출합니다.  
  
```  
BSCMAKE @prog1.txt  
```  
  
 다음은 샘플 명령 파일입니다.  
  
```  
/n /v /o main.bsc /El  
/S (  
toolbox.h  
verdate.h c:\src\inc\screen.h  
)  
file1.sbr file2.sbr file3.sbr file4.sbr  
```  
  
## 참고 항목  
 [BSCMAKE 참조](../../build/reference/bscmake-reference.md)