---
title: 매크로를 정의할 위치 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- defining macros
- macros, NMAKE
- NMAKE program, defining macros
ms.assetid: 0fc59ec5-5f58-4644-b7da-7b021f7001af
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9cf3e87a50362c770d45f00c4dc17ac3d264f611
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32380916"
---
# <a name="where-to-define-macros"></a>매크로를 정의할 위치
명령줄, 명령 파일 및 메이크파일 Tools.ini 파일에 매크로 정의 합니다.  
  
 메이크파일의 또는 Tools.ini 파일에서 각 매크로 정의 별도 줄에 표시 되 고 공백이 나 탭으로 시작할 수 없습니다. 공백이 나 탭 등호 앞뒤은 무시 됩니다. 모든 [자 문자열](../build/defining-an-nmake-macro.md) 리터럴 주변 따옴표와 포함 된 공백이 포함 됩니다.  
  
 명령줄 또는 명령 파일에서 공백 및 탭 인수를 구분 하 고 등호를 묶습니다 수 없습니다. 경우 `string` 공백이 나 탭에 포함 된 문자열 자체 또는 전체 매크로 큰따옴표로 묶습니다 ("").  
  
## <a name="see-also"></a>참고 항목  
 [NMake 매크로 정의](../build/defining-an-nmake-macro.md)