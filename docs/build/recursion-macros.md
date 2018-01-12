---
title: "재귀 매크로 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, recursion macros
- recursion macros
- macros, recursion
ms.assetid: c53e5ae7-619e-46b1-bdc2-86d8c7798b1d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e8d9ef7f194151fb3259712759d0c29ed157d564
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="recursion-macros"></a>재귀 매크로
재귀 매크로 사용 하 여 NMAKE를 재귀적으로 호출 합니다. 재귀 세션 Tools.ini 정보와 명령줄 및 환경 변수 매크로 상속합니다. 메이크파일 정의 유추 규칙을 상속 하지 않습니다 또는 **합니다. 접미사** 및 **합니다. 소중한** 사양입니다. 재귀 NMAKE 세션에 매크로 전달 하려면 설정 환경 변수 설정 된 재귀 호출 하기 전에, 재귀 호출에 대 한 명령에서 매크로 정의 하거나 Tools.ini에서 매크로 정의 합니다.  
  
|매크로|정의|  
|-----------|----------------|  
|**확인**|NMAKE를 호출을 위해 원래 사용 명령입니다.<br /><br /> $(MAKE) 매크로 nmake.exe를의 전체 경로 제공합니다.|  
|**MAKEDIR**|NMAKE가 호출 되었을 때 현재 디렉터리입니다.|  
|**MAKEFLAGS**|현재 적용 옵션입니다. 로 사용 하 여 `/$(MAKEFLAGS)`합니다.  /F 포함 되지 않습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [특수 NMake 매크로](../build/special-nmake-macros.md)