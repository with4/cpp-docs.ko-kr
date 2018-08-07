---
title: 사용 되지 않는 호출 규칙 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __fortran
- __pascal
- __syscall
dev_langs:
- C++
helpviewer_keywords:
- WINAPI [C++]
- __syscall keyword [C++]
- __pascal keyword [C++]
- __fortran keyword [C++]
- calling conventions, obsolete
ms.assetid: a91fc665-034a-48ce-b6bd-d27125f308a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 922103e808541e2829350749a04d6004ba36577f
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39403422"
---
# <a name="obsolete-calling-conventions"></a>사용되지 않는 호출 규칙
## <a name="microsoft-specific"></a>Microsoft 전용  
 합니다 **__pascal**를 **__fortran**, 및 **__syscall** 호출 규칙은 더 이상 지원 합니다. 지원되는 호출 규칙 및 적절한 링커 옵션 중 하나를 사용하여 해당 기능을 에뮬레이트할 수 있습니다.  
  
 \<windows.h > 이제 대상에 대 한 적절 한 호출 규칙으로 변환 되 WINAPI 매크로 지원 합니다. 이전에 사용한 PASCAL WINAPI 사용 하거나 **__far \__pascal**합니다.  
  
**Microsoft 전용 종료**  
  
## <a name="see-also"></a>참고자료  
 [인수 전달 및 명명 규칙](../cpp/argument-passing-and-naming-conventions.md)