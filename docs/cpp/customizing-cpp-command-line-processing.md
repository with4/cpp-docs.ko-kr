---
title: "C++ 명령줄 처리 사용자 지정 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_setenvp"
  - "_setargv"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_setargv 함수"
  - "_setenvp 함수"
  - "명령줄, 처리"
  - "명령줄, 인수 처리"
  - "명령줄 처리"
  - "환경, 환경 처리 루틴"
  - "시작 코드, 명령줄 처리 사용자 지정"
  - "환경 처리 표시하지 않음"
ms.assetid: aae01cbb-892b-48b8-8e1f-34f22421f263
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C++ 명령줄 처리 사용자 지정
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Microsoft 전용  
 프로그램에서 명령줄 인수를 사용하지 않는 경우 명령줄 처리를 수행하는 라이브러리 루틴의 사용을 억제하여 약간의 공간을 절약할 수 있습니다.  이 루틴은 **\_setargv**라고 하며 [와일드카드 확장](../cpp/wildcard-expansion.md)에서 설명합니다.  루틴의 사용을 억제하기 위해 **main** 함수를 포함하는 파일에서 아무 작업도 하지 않는 루틴을 정의하고 **\_setargv**를 명명합니다.  **\_setargv**에 대한 호출은 **\_setargv**의 정의로 충족되며 라이브러리 버전이 로드되지 않습니다.  
  
 마찬가지로 `envp` 인수를 통해 환경 테이블에 액세스하지 않을 경우 환경 처리 루틴인 **\_setenvp** 대신 사용할 수 있는 사용자 고유의 빈 루틴을 제공할 수 있습니다.  **\_setargv** 함수와 마찬가지로, **\_setenvp**는 **extern "C"**로 선언되어야 합니다.  
  
 프로그램은 C 런타임 라이브러리의 루틴 중 **spawn** 또는 `exec` 제품군에 대해 호출할 수 있습니다.  이런 경우에는 부모 프로세스에서 자식 프로세스로 환경을 전달하는 데 이 루틴이 사용되므로 환경 처리 루틴을 억제하면 안 됩니다.  
  
## Microsoft 전용 종료  
  
## 참고 항목  
 [main: 프로그램 시작](../cpp/main-program-startup.md)