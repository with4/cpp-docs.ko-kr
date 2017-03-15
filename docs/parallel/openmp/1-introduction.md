---
title: "1. Introduction | Microsoft Docs"
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
ms.assetid: c42e72bc-0e31-4b1c-b670-cd82673c0c5a
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 1. Introduction
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 문서 컴파일러 지시문, 라이브러리 함수를 C와 C\+\+ 프로그램에서 공유 메모리 병렬 처리를 지정 하는 데 사용할 수 있는 환경 변수 집합을 지정 합니다.  이 문서에서 설명 하는 기능으로 통칭 되는  *OpenMP C\/C\+\+ 응용 프로그램 인터페이스 \(API\)*.  병렬 프로그래밍을 위한 모델을 제공 합니다 프로그램 공유 메모리 아키텍처에서 서로 다른 공급 업체 간에 이동할 수 있습니다이 사양의 목표가입니다.  C\/C\+\+ OpenMP API 컴파일러로 다양 한 공급 업체에서 지원 됩니다.  OpenMP에 대 한 자세한 정보 포함 하는  *OpenMP 포트란 응용 프로그램 인터페이스*, 다음 웹 사이트에서 찾을 수 있습니다:  
  
 [http:\/\/www.openmp.org](http://www.openmp.org)  
  
 지시문, 라이브러리 함수 및이 문서에서 정의 된 환경 변수 만드는 휴대성을 허용 하는 동안 병렬 프로그램을 관리 하는 사용자 수 있습니다.  지시문을 C 확장 및 순차 C\+\+ 프로그래밍 모델이 단일 프로그램을 여러 데이터 \(SPMD\) 구조, 구조 작업 공유 및 동기화 구문을 공유 및 데이터 화에 대 한 지원을 제공 합니다.  OpenMP C 및 C\+\+ API를 지 원하는 컴파일러를 활성화 하 고 모든 OpenMP 컴파일러 지시문의 해석을 허용 컴파일러 명령줄 옵션을 포함 됩니다.