---
title: BSCMAKE을 빌드하는 방법에 있습니다. Bsc 파일 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- browse information files (.bsc), building
ms.assetid: 8512b33e-c856-44a2-87bd-01ab10b52a95
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0cdc8a2840e3beb1272b33b2794f70a979684f46
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373490"
---
# <a name="how-bscmake-builds-a-bsc-file"></a>BSCMAKE에서 .Bsc 파일을 빌드하는 방법
BSCMAKE 빌드하거나 수 있는 가장 효율적인 방법으로.bsc 파일을 다시 빌드합니다. 잠재적 문제를 방지 하려면 빌드 프로세스를 이해 하는 것이 중요 합니다.  
  
 BSCMAKE 찾아보기 정보 파일을 빌드할 때.sbr 파일을 길이 0으로 자릅니다. 다음에 동일한 파일을 빌드하는 동안 빈 (또는 비어 있음).sbr 파일은 BSCMAKE 해당.sbr 파일에 없는 새 하도록 지시 합니다. BSCMAKE는 파일의 해당 부분을 업데이트 하는 필요 하지 않습니다. 증분 빌드 적용 됩니다. 알 수 있습니다. 모든 빌드 중 (/n 옵션 지정 되지 않은 경우), BSCMAKE는 변경 된.sbr 파일만 사용 하 여 파일을 증분 방식으로 업데이트 하려면 먼저 시도 합니다.  
  
 BSCMAKE /o 옵션에 지정 된 이름을 가진.bsc 파일을 찾습니다. /O를 지정 하지 않으면 BSCMAKE.bsc 확장명 첫 번째.sbr 파일의 기본 이름을 가진 파일을 찾습니다. 파일이 있으면 BSCMAKE만 영향을 주는.sbr 파일을 사용 하 여 찾아보기 정보 파일의 증분 빌드를 수행 합니다. 파일이 없으면 BSCMAKE 모든.sbr 파일을 사용 하 여 전체 빌드를 수행 합니다. 빌드에 대 한 규칙은 다음과 같습니다.  
  
-   성공 하려면 전체 빌드를 모두 지정.sbr 파일이 존재 해야 하며 잘리지 않아야 합니다. .Sbr 파일 잘리는 경우 빌드해야 것 (다시 컴파일하거나)에서 BSCMAKE를 실행 하기 전에.  
  
-   성공 하려면 증분 빌드는.bsc 파일이 존재 해야 합니다. 모든.sbr 파일이, 빈 파일에도 존재 해야 하며 BSCMAKE 명령줄에 지정 해야 합니다. 명령줄에서.sbr 파일을 생략 하면 BSCMAKE의 구성 파일에서 제거 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [.Bsc 파일 빌드](../../build/reference/building-a-dot-bsc-file.md)