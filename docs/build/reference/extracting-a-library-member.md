---
title: "라이브러리 멤버 추출 | Microsoft Docs"
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
  - "Lib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/EXTRACT 라이브러리 관리자 옵션"
  - "EXTRACT 라이브러리 관리자 옵션"
  - "-EXTRACT 라이브러리 관리자 옵션"
  - "라이브러리 멤버 추출"
  - "LIB[C++], 라이브러리 멤버 추출"
  - "라이브러리, 멤버 추출"
ms.assetid: a2c5c2a1-9b7e-489a-a9a4-1dec694e1fc5
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 라이브러리 멤버 추출
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

LIB를 사용하여 기존 라이브러리의 멤버 복사본이 들어 있는 개체\(.obj\) 파일을 만들 수 있습니다.  멤버 복사본을 추출하려면 다음 구문을 사용합니다.  
  
```  
LIB library /EXTRACT:member /OUT:objectfile  
```  
  
 이 명령을 사용하면 *library*의 `member` 복사본이 들어 있는 *objectfile*이라는 .obj 파일이 만들어집니다.  `member` 이름은 대\/소문자가 구분됩니다.  하나의 명령으로는 하나의 멤버만 추출할 수 있습니다.  기본 출력 이름이 없기 때문에 \/OUT 옵션은 필수 요소입니다.  지정된 디렉터리\(*objectfile*과 함께 지정된 디렉터리가 없는 경우에는 현재 디렉터리\)에 *objectfile*이라는 파일이 이미 있는 경우에는 추출된 *objectfile*이 기존 파일을 대체합니다.  
  
## 참고 항목  
 [LIB 참조](../../build/reference/lib-reference.md)