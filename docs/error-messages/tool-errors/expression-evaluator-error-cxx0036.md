---
title: "식 계산기 오류 CXX0036 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "CXX0036"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAN0036"
  - "CXX0036"
ms.assetid: 383404be-df5b-4eec-b113-df21bb5d269d
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 식 계산기 오류 CXX0036
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

잘못된 컨텍스트{...} 사양입니다.  
  
 이 메시지는 컨텍스트 연산자\(**{{**\)를 잘못 사용할 때 생성될 수 있습니다.  
  
-   컨텍스트 연산자\(**{{**\)의 구문이 올바르지 않습니다.  
  
     컨텍스트 연산자의 구문은 다음과 같습니다.  
  
     {*function*,*module*,*dll*}*expression*  
  
     expression의 컨텍스트를 지정합니다.  컨텍스트 연산자는 형식 변환과 우선 순위 및 사용법이 같습니다.  
  
     뒤의 쉼표를 생략할 수 있습니다.  function, module 또는 dll 중에 리터럴 쉼표가 들어 있는 경우 전체 이름을 괄호로 묶어야 합니다.  
  
-   함수 이름의 맞춤법이 잘못되었거나 지정한 모듈 또는 동적 연결 라이브러리에 함수가 없습니다.  
  
     C는 대\/소문자를 구분하는 언어이므로 function은 소스에 정의된 대로 대\/소문자를 정확하게 지정해야 합니다.  
  
-   모듈 또는 DLL을 찾을 수 없습니다.  
  
     지정한 모듈 또는 DLL의 전체 경로 이름을 확인하십시오.  
  
 이 오류는 CAN0036과 동일합니다.