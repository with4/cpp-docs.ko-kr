---
title: "연결 된 해제 정보 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 176835bf-f118-45d9-9128-9db4b7571864
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3ac09c1f107b51542b7a17c8661eb784b4abf14a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="chained-unwind-info-structures"></a>연결된 해제 정보 구조체
UNW_FLAG_CHAININFO 플래그가 설정 된 경우, 해제 정보 구조체는 보조 로케이터로 되 고 주 해제 정보를 포함 하는 공유 되는 예외-처리기/연결 된 정보 주소 필드. 다음 코드를 검색 주 정보를 가정 하 고 해제 `unwindInfo` 는 UNW_FLAG_CHAININFO이 있는 구조 플래그가 설정 됩니다.  
  
```  
PRUNTIME_FUNCTION primaryUwindInfo = (PRUNTIME_FUNCTION)&(unwindInfo->UnwindCode[( unwindInfo->CountOfCodes + 1 ) & ~1]);  
```  
  
 연결 된 정보는 두 가지 상황에서 유용 합니다. 첫째, 불연속 코드 세그먼트에 사용할 수 있습니다. 연결 된 정보를 사용 하 여 주 해제 정보에서 해제 코드 배열을 복제 하려면 없기 때문에 필요한 해제 정보의 크기를 줄일 수 있습니다.  
  
 휘발성 레지스터 저장을 그룹화 할 연결 된 정보를 사용할 수도 있습니다. 컴파일러는 함수 항목 프롤로그의 외부에 있을 때까지 일부 휘발성 레지스터의 저장 지연 될 수 있습니다. 그룹화 된 코드 보다 먼저 함수의 부분에 대 한 주 해제까지 기록할 수 있습니다 하 고 0이 아닌 크기 프롤로그에 연결 된 정보에서 비휘발성 레지스터의 정보를 연결로 설정 합니다. 이 경우 해제 코드는 UWOP_SAVE_NONVOL의 모든 인스턴스입니다. 푸시를 사용 하 여 비휘발성 레지스터를 저장 하거나 추가 고정된 스택 할당을 사용 하 여 RSP 레지스터를 수정 하는 그룹화는 지원 되지 않습니다.  
  
 설정 UNW_FLAG_CHAININFO UNWIND_INFO 항목 UNWIND_INFO 항목이 역시 (여러 축소 래핑) 설정 UNW_FLAG_CHAININFO RUNTIME_FUNCTION 항목을 포함할 수 있습니다. 결국는 연결 된 해제 정보를 지워 UNW_FLAG_CHAININFO UNWIND_INFO 항목에 도달 하는 포인터 이것이 실제 프로시저 진입점을 가리키는 기본 UNWIND_INFO 항목입니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버거 지원, 예외 처리를 위한 해제 데이터](../build/unwind-data-for-exception-handling-debugger-support.md)