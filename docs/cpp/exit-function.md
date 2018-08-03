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
ms.openlocfilehash: ce4272ecfee4b3d02d8bf79f7816200a392c9735
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404830"
---
# <a name="exit-function"></a>exit 함수
**종료** 표준 포함 파일에 선언 된 함수 \<b. h >, c + + 프로그램을 종료 합니다.  
  
 인수로 제공 된 값 **종료** 프로그램의 반환 코드 또는 종료 코드로 서 운영 체제에 반환 됩니다. 규칙에 따라 반환 코드 0은 프로그램이 성공적으로 완료되었음을 의미합니다.  
  
> [!NOTE]
>  EXIT_FAILURE 및 아니거나 EXIT_SUCCESS에 정의 된 상수를 사용할 수 있습니다 \<b. h >, 프로그램의 성공 또는 실패를 나타냅니다.  
  
 발급을 **반환** 문을 `main` 함수 호출에 해당 하는 합니다 **종료** 인수로 반환 값을 사용 하 여 함수.  
  
 자세한 내용은 [종료](../c-runtime-library/reference/exit-exit-exit.md) 에 *런타임 라이브러리 참조*합니다.  
  
## <a name="see-also"></a>참고자료  
 [프로그램 종료](../cpp/program-termination.md)