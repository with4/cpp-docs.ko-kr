---
title: "디버그 빌드를 사용한 메모리 덮어쓰기 확인 | Microsoft Docs"
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
  - "메모리, 덮어쓰기"
ms.assetid: 1345eb4d-24ba-4595-b1cc-2da66986311e
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 디버그 빌드를 사용한 메모리 덮어쓰기 확인
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

메모리 덮어쓰기 발생 여부를 확인하는 데 디버그 빌드를 사용하려면 먼저 프로젝트를 디버깅할 수 있도록 다시 빌드해야 합니다.  그런 다음 응용 프로그램에 있는 `InitInstance` 함수의 맨 처음 부분에 다음 줄을 추가합니다.  
  
```  
afxMemDF |= checkAlwaysMemDF;  
```  
  
 이렇게 하면 디버그 메모리 할당자가 모든 할당된 메모리 주위에 보호 바이트를 배치합니다.  그러나 이 보호 바이트의 변경 여부\(변경되었으면 메모리 덮어쓰기가 발생했음\)를 확인하지 않으면 보호 바이트는 아무런 소용이 없습니다.  보호 바이트의 변경 여부를 확인하면 버퍼가 제공되어 메모리 덮어쓰기를 해결할 수 있습니다.  
  
 `checkAlwaysMemDF` 변수를 설정하면 MFC에서는 **new** 또는 **delete**가 호출될 때마다 `AfxCheckMemory` 함수를 호출하게 됩니다.  메모리 덮어쓰기가 감지된 경우에는 다음과 같은 TRACE 메시지가 생성됩니다.  
  
```  
Damage Occurred! Block=0x5533  
```  
  
 이러한 메시지가 표시되는 경우에는 코드를 단계별로 실행하여 손상된 부분을 확인해야 합니다.  메모리 덮어쓰기가 발생한 부분을 보다 정확하게 구별하려면 사용자가 `AfxCheckMemory`를 명시적으로 호출하면 됩니다.  예를 들면 다음과 같습니다.  
  
```  
ASSERT(AfxCheckMemory());  
    DoABunchOfStuff();  
    ASSERT(AfxCheckMemory());  
```  
  
 첫 번째 ASSERT는 성공하고 두 번째 ASSERT는 실패하는 경우에는 두 호출 사이의 함수에서 메모리 덮어쓰기가 발생했을 가능성이 큽니다.  
  
 응용 프로그램의 특성에 따라 `afxMemDF`를 사용하면 프로그램 실행이 너무 느려져서 테스트조차 수행할 수 없는 경우도 있습니다.  왜냐하면`afxMemDF` 변수는 new 및 delete가 호출될 때마다 `AfxCheckMemory`가 호출되도록 하기 때문입니다.  이 경우에는 위의 예제와 같이 `AfxCheckMemory`\( \) 호출을 분산시켜야 하며, 이러한 방법으로 메모리 덮어쓰기를 구별해야 합니다.  
  
## 참고 항목  
 [릴리스 빌드 문제 해결](../../build/reference/fixing-release-build-problems.md)