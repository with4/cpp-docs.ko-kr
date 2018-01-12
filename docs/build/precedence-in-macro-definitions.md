---
title: "매크로 정의의 우선 순위 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, precedence in macro definitions
- macros, precedence
ms.assetid: 0c13182d-83cb-4cbd-af2d-f4c916b62aeb
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7421ef51c37e3724bdb986321581e6736a62e18b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="precedence-in-macro-definitions"></a>매크로 정의의 우선 순위
NMAKE는 매크로 정의가 여러 개 있으면, 우선 순위가 가장 높은 정의 사용 합니다. 다음 목록은 내림차순 우선 순위를 나타냅니다.  
  
1.  명령줄에 정의 된 매크로  
  
2.  매크로 메이크파일에 정의 된 또는 파일 포함  
  
3.  상속 된 환경 변수 매크로  
  
4.  Tools.ini 파일에 정의 된 매크로  
  
5.  미리 정의 된 매크로 같은 [CC](../build/command-macros-and-options-macros.md) 및 [AS](../build/command-macros-and-options-macros.md)  
  
 /E 동일한 이름 가진 메이크파일 매크로 재정의 하려면 환경 변수에서 상속 하는 매크로를 사용 합니다. 사용 하 여 **! UNDEF** 명령줄을 재정의 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [NMake 매크로 정의](../build/defining-an-nmake-macro.md)