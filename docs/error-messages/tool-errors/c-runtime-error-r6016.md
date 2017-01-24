---
title: "C 런타임 오류 R6016 | Microsoft Docs"
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
  - "R6016"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6016"
ms.assetid: 7bd3f274-d9c4-4bc4-8252-80bf168c4c3a
caps.latest.revision: 12
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C 런타임 오류 R6016
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

스레드 데이터에 대한 공간이 부족합니다.  
  
> [!NOTE]
>  이 오류 메시지를 발견하는 경우 내부 메모리에 문제가 있기 때문에 명명된 프로그램이 종료된 것입니다.  이 오류가 발생할 수 있는 이유는 여러 가지가 있지만 대개 프로그램의 결함 또는 프로그램이 사용하는 Visual C\+\+ 라이브러리의 손상이 원인입니다.  
>   
>  이 오류를 해결하려면 다음 단계를 시도할 수 있습니다.  
>   
>  -   **제어판**의 **프로그램 및 기능** 페이지를 사용하여 프로그램을 복구하거나 다시 설치합니다.  
> -   **제어판**의 **프로그램 및 기능** 페이지를 사용하여 Microsoft Visual C\+\+ 재배포 가능 파일의 모든 복사본을 복구하거나 다시 설치합니다.  
> -   소프트웨어 업데이트를 위해 **제어판**의 **Windows 업데이트**를 선택합니다.  
> -   프로그램의 업데이트 버전이 있는지 확인합니다.  
  
 이 오류가 발생하는 이유는 프로그램이 운영 체제에서 [\_beginthread](../../c-runtime-library/reference/beginthread-beginthreadex.md) 또는 `_beginthreadex` 호출을 완료할 충분한 메모리를 받지 못했거나 스레드 로컬 저장소가 `_beginthread` 또는 `_beginthreadex`에 의해 초기화되지 않았기 때문입니다.  
  
 새 스레드가 시작되면 라이브러리는 해당 스레드에 대한 내부 데이터베이스를 만들어야 합니다.  데이터베이스가 운영 체제에서 제공한 메모리를 사용하여 확장할 수 없으면 스레드가 시작되지 않으며 호출 프로세스는 중지됩니다.  프로세스에 의해 너무 많은 스레드가 만들어졌거나 스레드 로컬 저장소를 모두 사용한 경우 이러한 현상이 발생할 수 있습니다.  
  
 C 런타임 라이브러리\(CRT\)를 호출하는 실행 파일은 스레드를 만들 때 Windows API `CreateThread`가 아니라 `_beginthreadex`를 사용하는 것이 좋습니다.  `_beginthreadex`는 스레드 로컬 저장소의 많은 CRT 함수에 의해 사용되는 내부 정적 저장소를 초기화합니다.  `CreateThread`를 사용하여 스레드를 만드는 경우 초기화된 내부 정적 저장소가 필요한 CRT 함수를 호출할 때 CRT는 R6016으로 프로세스를 종료할 수 있습니다.