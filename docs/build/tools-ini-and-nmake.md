---
title: Tools.ini와 NMAKE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, reading files
- Tools.ini and NMake
ms.assetid: ebd5eab6-ddf4-430e-bf4a-1db5bb84e344
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 860a334274a3a1a4ac9e11c3e7b5e9a0f136ecc0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="toolsini-and-nmake"></a>Tools.ini와 NMAKE
NMAKE 읽습니다 Tools.ini 메이크파일에 읽기 전에 /R 사용 되지 않은 경우. 찾습니다 Tools.ini 먼저 현재 디렉터리에서 찾은 다음 INIT 환경 변수로 지정 된 디렉터리에서. NMAKE 설정 초기화 파일의 섹션으로 시작 `[NMAKE]` 메이크파일 정보를 포함할 수 있습니다. # 기호로 시작 하는 별도 줄에 주석을 지정 (#).  
  
## <a name="see-also"></a>참고 항목  
 [NMAKE 실행](../build/running-nmake.md)