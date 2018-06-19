---
title: 구조체 RUNTIME_FUNCTION | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 84386527-d3aa-41c5-871d-78e3e1913704
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3c2f28380d4a14cf7617653ede20468c45649a8b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379928"
---
# <a name="struct-runtimefunction"></a>구조체 RUNTIME_FUNCTION
테이블 기반 예외 처리 스택 공간을 할당 하거나 다른 함수 (예를 들어 리프가 아닌 함수)를 호출 하는 모든 기능을 위한 테이블 항목을 필요 합니다. 함수 테이블 항목의 형식을 갖습니다.  
  
|||  
|-|-|  
|ULONG|함수 시작 주소|  
|ULONG|끝 주소 함수|  
|ULONG|정보 주소를 해제 합니다.|  
  
 구조체 RUNTIME_FUNCTION DWORD 메모리에 정렬 해야 합니다. 모든 주소는 상대 이미지, 즉, 함수 테이블 항목을 포함 하는 이미지의 시작 주소에서 32 비트 오프셋 됩니다. 이러한 항목은 정렬 되며 PE32 + 이미지의.pdata 섹션에 놓여집니다. 동적으로 생성 된 함수 [JIT 컴파일러]에 대 한 이러한 함수를 지원 하기 위해 런타임 해야 RtlInstallFunctionTableCallback 또는 사용할 RtlAddFunctionTable 운영 체제에이 정보를 제공. 신뢰할 수 없는 예외 처리 및 프로세스 디버깅 하지 못하면 발생 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버거 지원, 예외 처리를 위한 해제 데이터](../build/unwind-data-for-exception-handling-debugger-support.md)