---
title: "NMAKE 실행 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- targets, building
- response files, NMAKE
- targets
- command files
- NMAKE program, targets
- NMAKE program, running
- command files, NMAKE
ms.assetid: 0421104d-8b7b-4bf3-86c1-928d9b7c1a8c
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a6c39612cf4df47665f7ea3d529b77ee4e70ce8a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="running-nmake"></a>NMAKE 실행
## <a name="syntax"></a>구문  
  
```  
NMAKE [option...] [macros...] [targets...] [@commandfile...]  
```  
  
## <a name="remarks"></a>설명  
 NMAKE 빌드만 지정 *대상* 또는 첫 번째 메이크파일의 대상으로 지정 되지 않은 경우. 첫 번째 메이크파일 대상이 될 수 있습니다는 [의사 대상](../build/pseudotargets.md) 다른 대상을 빌드합니다입니다. NMAKE 메이크파일 /F;로 지정 된 사용 /F 지정 되지 않은 경우 현재 디렉터리의 메이크파일 파일을 사용 합니다. 유추 규칙 사용 하 여 명령줄 빌드를 지정 된 메이크파일이 없는 경우 *대상*합니다.  
  
 `commandfile` 명령줄 입력이 포함 된 텍스트 파일 (또는 지시 파일). 다른 입력 앞 또는 뒤`commandfile`합니다. 경로 사용할 수 있습니다. `commandfile`, 줄 바꿈 공백으로 처리 됩니다. 공백이 포함 되어 매크로 정의를 따옴표로 묶습니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>추가 정보  
 [NMAKE 옵션](../build/nmake-options.md)  
  
 [Tools.ini 및 NMake](../build/tools-ini-and-nmake.md)  
  
 [NMAKE의 종료 코드](../build/exit-codes-from-nmake.md)  
  
## <a name="see-also"></a>참고 항목  
 [NMAKE 참조](../build/nmake-reference.md)