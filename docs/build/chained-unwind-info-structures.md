---
title: "연결된 해제 정보 구조체 | Microsoft Docs"
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
ms.assetid: 176835bf-f118-45d9-9128-9db4b7571864
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 연결된 해제 정보 구조체
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

UNW\_FLAG\_CHAININFO 플래그가 설정되어 있으면 해제 정보 구조는 보조 정보이고 공유되는 예외 처리기\/연결된 정보 주소 필드에 주 정보 해제를 포함합니다.  다음 코드는 주 정보 해제를 검색하여 `unwindInfo`이 UNW\_FLAG\_CHAININFO 플래그가 설정된 구조임을 가정합니다.  
  
```  
PRUNTIME_FUNCTION primaryUwindInfo = (PRUNTIME_FUNCTION)&(unwindInfo->UnwindCode[( unwindInfo->CountOfCodes + 1 ) & ~1]);  
```  
  
 연결된 정보는 두 가지 상황에서 유용합니다.  첫 번째로 불연속 코드 세그먼트에 사용할 수 있습니다.  연결된 정보를 사용하면 주 해제 정보에서 해제 코드를 복제할 필요가 없기 때문에 필요한 해제 정보의 크기를 줄일 수 있습니다.  
  
 연결된 정보를 사용하여 volatile 레지스터 저장을 그룹화할 수도 있습니다.  컴파일러는 함수 진입점 프롤로그의 외부에 도달할 때까지 일부 volatile 레지스터의 저장을 지연시킬 수도 있습니다.  함수에서 그룹화된 코드가 나오기 전까지 주 해제 정보를 사용한 다음 프롤로그 크기가 0이 아닌 연결된 정보를 설정하면 이러한 동작을 기록할 수 있습니다. 여기서 연결된 정보의 해제 코드는 비volatile 레지스터의 저장을 반영합니다.  이 경우 해제 코드는 모두 UWOP\_SAVE\_NONVOL의 인스턴스입니다.  밀어넣기를 사용 하 여 비 volatile 레지스터를 저장 하거나 추가 고정된 스택 할당을 통해 RSP 레지스터를 수정 하는 그룹은 지원 되지 않습니다.  
  
 UNW\_FLAG\_CHAININFO가 있는 UNWIND\_INFO 항목은 마찬가지로 UNWIND\_INFO 항목에 UNW\_FLAG\_CHAININFO가 설정된 RUNTIME\_FUNCTION 진입점을 포함할 수 있습니다. 이것을 다중 축소 래핑이라고 합니다.  연결된 해제 정보 포인터를 추적하면 결국 UNW\_FLAG\_CHAININFO가 설정되지 않은 UNWIND\_INFO 항목에 이르게 됩니다. 이 항목이 실제 프로시저 진입점을 가리키는 주 UNWIND\_INFO 항목입니다.  
  
## 참고 항목  
 [예외 처리 및 디버거 지원을 위한 해제 데이터](../build/unwind-data-for-exception-handling-debugger-support.md)