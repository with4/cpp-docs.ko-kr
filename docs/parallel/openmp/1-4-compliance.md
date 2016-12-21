---
title: "1.4 규격 | Microsoft Docs"
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
ms.assetid: 662ad260-b9a1-43b7-b269-ef6ff0714e05
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 1.4 규격
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OpenMP C/c + + API의 구현은 *OpenMP 규격* 경우 인식 하 고 단원 1, 2, 3, 4에 따라이 사양의 모든 요소의 의미 체계를 유지 및 부록 3. 부록 A "," B "," D "," E "및" F는 정보용 으로만 설정 되며 사양에 포함 되지 않습니다. API의 하위 집합만 포함 하는 구현을 OpenMP 규격이 아닙니다.  
  
 OpenMP C 및 c + + API는 확장 구현에서 지원 되는 기본 언어입니다. 기본 언어는이 문서에는 언어 구문 또는 확장에 표시를 지원 하지 않으면, OpenMP 구현 지원 않아도 됩니다.  
  
 모든 표준 C 및 c + + 라이브러리 함수 및 기본 제공 함수 (즉, 함수는 컴파일러는 특정 기술 자료) 스레드로부터 안전 해야 합니다. 병렬 영역 내에 다른 스레드에서 스레드 – 안전 기능을 사용 하는 동기화 되지 않은 동작이 생성 되지 않습니다. 그러나 동작 수 되지 직렬 지역에서와 동일 합니다. (난수 생성 함수는 예입니다.)  
  
 OpenMP C/c + + API 지정 동작은 특정 *구현 정의 합니다.* 표준에 맞는 OpenMP 구현은 정의 하 고 이러한 경우에 따라 동작을 문서화 하는 일을 해야 합니다. 참조 [부록 E](../../parallel/openmp/e-implementation-defined-behaviors-in-openmp-c-cpp.md), 97, 구현 정의 동작의 목록에 대 한 페이지입니다.