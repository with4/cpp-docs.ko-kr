---
title: 함수 형식 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 7e33d5f4-dabb-406d-afb3-13777b995028
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 322bd45abbfe217671fd39f0617987fde21445db
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="function-types"></a>함수 형식
두 형식의 함수는 기본적으로 합니다. 스택 프레임을 필요로 하는 함수에는 프레임 함수를 라고 합니다. 스택 프레임은 필요 하지 않은 함수에는 리프 함수를 호출 됩니다.  
  
 프레임 함수에 스택 공간이 할당 되는, 다른 함수를 호출 하 고 비휘발성 레지스터를 저장 하거나 예외 처리를 사용 하는 함수가입니다. 또한 함수 테이블 항목을 필요합니다. 프레임 함수 프롤로그와 에필로그가 필요합니다. 프레임 함수 스택 공간을 동적으로 할당 하 고 프레임 포인터를 사용할 수 있습니다. 프레임 함수 호출에이의 전체 기능에 있습니다.  
  
 프레임 함수가 다른 함수를 호출 하지 경우 스택에 맞게 필요는 없습니다 (섹션에서 언급 된 [스택 할당](../build/stack-allocation.md)).  
  
 리프 함수는 함수 테이블 항목을 필요 하지 않습니다. RSP 함수를 호출할 수 없습니다 또는 스택 공간을 할당 하는 등의 모든 비휘발성 레지스터를 변경할 수 없습니다 것입니다. 실행 하는 동안 스택 정렬 되지 않은 상태로 허용 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [스택 사용](../build/stack-usage.md)
