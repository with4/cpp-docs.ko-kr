---
title: 명령 한정자 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, command modifiers
- command modifiers
ms.assetid: b661c432-210f-4f05-bc56-744a46e0fc0b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3739c053797bdccd08310e17bf669413ead0db48
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367175"
---
# <a name="command-modifiers"></a>명령 한정자
명령 앞에 공백이 나 탭으로 구분 된 필요에 따라 하나 이상의 명령 한정자를 지정할 수 있습니다. 명령과 마찬가지로 한정자를 써야 합니다.  
  
|한정자|용도|  
|--------------|-------------|  
|@*명령*|명령 표시를 하지 않습니다. 명령 사용 하 여 디스플레이 표시 됩니다. NMAKE는 기본적으로 실행 된 모든 명령을 표시합니다. /S를 사용 하 여 전체 메이크파일; 표시 하지 않으려면 사용 하 여 **합니다. 자동** 메이크파일의 부분에 대 한 표시 하지 않으려면입니다.|  
|**-**[`number` ]*명령*|오류에 대 한 검사를 해제 *명령*합니다. 기본적으로 NMAKE 명령이 0이 아닌 종료 코드를 반환 하면 중지 됩니다. If-`number` 는 종료 코드를 초과 하는 경우 NMAKE 중지을 사용 하는 `number`합니다. 공백이 나 탭에 대시를 사이 사용할 수 없습니다 및 *번호입니다.* 하나 이상의 공백 또는 탭 사이 나타나야 합니다 `number` 및 *명령*합니다. /I를 사용 하 여 오류 전체 메이크파일;에 대 한 검사를 해제 하려면 사용 하 여 **합니다. 무시** 오류 메이크파일의 부분에 대 한 검사를 해제 하려면.|  
|**!** *command*|실행 *명령* 각 종속 파일에 대 한 경우 *명령* 사용 하 여 **$ \* \*** (종속성의 모든 종속 파일) 또는 **$?** (모든 종속 파일에 대 한 타임 스탬프가).|  
  
## <a name="see-also"></a>참고 항목  
 [메이크파일의 명령](../build/commands-in-a-makefile.md)