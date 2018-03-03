---
title: "exit 함수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- Exit
dev_langs:
- C++
helpviewer_keywords:
- exit function
ms.assetid: 26ce439f-81e2-431c-9ff8-a09a96f32127
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ee6a34a70465904e6725f42e68eb4a00c03a1661
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2018
---
# <a name="exit-function"></a>exit 함수
**종료** 표준 포함 파일에 선언 된 함수 \<stdlib.h >, c + + 프로그램을 종료 합니다.  
  
 에 대 한 인수로 제공 된 값 **종료** 프로그램의 반환 코드 또는 종료 코드로 서 운영 체제에 반환 됩니다. 규칙에 따라 반환 코드 0은 프로그램이 성공적으로 완료되었음을 의미합니다.  
  
> [!NOTE]
>  상수를 사용할 수 `EXIT_FAILURE` 및 `EXIT_SUCCESS`에 정의 된 \<stdlib.h > 프로그램의 성공 또는 실패를 나타내기 위해.  
  
 발급 한 `return` 에서 문을 **주** 함수 호출에 해당 하는 **종료** 함수 인수로 서 값을 반환 합니다.  
  
 자세한 내용은 참조 [종료](../c-runtime-library/reference/exit-exit-exit.md) 에 *런타임 라이브러리 참조*합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로그램 종료](../cpp/program-termination.md)