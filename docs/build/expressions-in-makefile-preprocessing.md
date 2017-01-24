---
title: "메이크파일 전처리 식 | Microsoft Docs"
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
  - "식[C++], 메이크파일 전처리"
  - "메이크파일, 전처리"
  - "메이크파일 전처리"
ms.assetid: 37f0f413-97e0-452c-a83f-3c9002c44c92
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 메이크파일 전처리 식
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**\!IF** 또는 **\!ELSE IF** `constantexpression`은 정수형 상수\(십진수나 C 언어 표기법으로 표기됨\), 문자열 또는 명령으로 구성됩니다.  식을 그룹으로 묶으려면 괄호를 사용합니다.  식은 C 스타일의 부호 있는 long integer 산술 형식이며 숫자는 범위가 2147483648 \- 2147483647인 32비트 2의 보수 형식입니다.  
  
 식에 상수 값에 적용되는 연산자, 명령의 종료 코드, 문자열, 매크로 및 파일 시스템 경로를 사용할 수 있습니다.  
  
## 추가 정보  
 [메이크파일 전처리 연산자](../build/makefile-preprocessing-operators.md)  
  
 [전처리에서 프로그램 실행](../build/executing-a-program-in-preprocessing.md)  
  
## 참고 항목  
 [메이크파일 전처리](../build/makefile-preprocessing.md)