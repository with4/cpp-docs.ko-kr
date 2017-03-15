---
title: "1.1 Scope | Microsoft Docs"
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
ms.assetid: a8570a3c-1dd6-4c3d-b368-a10fcb3534a6
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 1.1 Scope
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 사양은 사용자 조정 병렬화 컴파일러와 런타임 시스템에서 병렬 프로그램을 실행 하기 위해 수행할 작업은 사용자가 명시적으로 지정 하는 사태가 다룹니다.  OpenMP C 및 C\+\+ 구현은 종속성, 충돌, 교착 상태, 경합 상태 또는 잘못 된 프로그램이 실행 하는 다른 문제에 대 한 확인 필요는 없습니다.  사용자는 OpenMP C 및 C\+\+ API 구문을 사용 하 여 응용 프로그램이 제대로 실행 되도록 하는 데 담당 합니다.  컴파일러에서 생성 된 자동 병렬 처리 기능 및 이러한 병렬 처리를 지원 하기 위해 사용 하는 컴파일러 지시문이이 문서에서 다루지 않습니다.