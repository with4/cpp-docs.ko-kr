---
title: exit 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- Exit
dev_langs:
- C++
helpviewer_keywords:
- exit function
ms.assetid: 26ce439f-81e2-431c-9ff8-a09a96f32127
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d08ac1375fa383543eaafb5b3ce49cd2bbfbc4da
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37941082"
---
# <a name="exit-function"></a>exit 함수
`exit` 표준 포함 파일에 선언 된 함수 \<b. h >, c + + 프로그램을 종료 합니다.  
  
 인수로 제공 된 값 `exit` 프로그램의 반환 코드 또는 종료 코드로 서 운영 체제에 반환 됩니다. 규칙에 따라 반환 코드 0은 프로그램이 성공적으로 완료되었음을 의미합니다.  
  
> [!NOTE]
>  EXIT_FAILURE 및 아니거나 EXIT_SUCCESS에 정의 된 상수를 사용할 수 있습니다 \<b. h >, 프로그램의 성공 또는 실패를 나타냅니다.  
  
 발급을 **반환** 문을 합니다 `main` 함수 호출에 해당 하는 `exit` 인수로 반환 값을 사용 하 여 함수.  
  
 자세한 내용은 [종료](../c-runtime-library/reference/exit-exit-exit.md) 에 *런타임 라이브러리 참조*합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로그램 종료](../cpp/program-termination.md)