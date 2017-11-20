---
title: "Tools.ini와 NMAKE | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, reading files
- Tools.ini and NMake
ms.assetid: ebd5eab6-ddf4-430e-bf4a-1db5bb84e344
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 638132f640fd342a752ec45541275178f6f26692
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="toolsini-and-nmake"></a>Tools.ini와 NMAKE
NMAKE 읽습니다 Tools.ini 메이크파일에 읽기 전에 /R 사용 되지 않은 경우. 찾습니다 Tools.ini 먼저 현재 디렉터리에서 찾은 다음 INIT 환경 변수로 지정 된 디렉터리에서. NMAKE 설정 초기화 파일의 섹션으로 시작 `[NMAKE]` 메이크파일 정보를 포함할 수 있습니다. # 기호로 시작 하는 별도 줄에 주석을 지정 (#).  
  
## <a name="see-also"></a>참고 항목  
 [NMAKE 실행](../build/running-nmake.md)