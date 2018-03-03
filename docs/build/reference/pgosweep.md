---
title: pgosweep | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- pgosweep program
- profile-guided optimizations, pgosweep
ms.assetid: f39dd3b7-1cd9-4c3b-8e8b-fb794744b757
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 78ae6c36011e3c10359988cf2c501514d1bcf70a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="pgosweep"></a>pgosweep
.Pgc 파일에 실행 중인 프로그램에서 모든 프로필 데이터를 쓰는 데 프로필 기반 최적화에 사용 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
pgosweep [options] image pgcfile  
```  
  
#### <a name="parameters"></a>매개 변수  
 `options`  
 비워 둘 수 있는 선택적 매개 변수입니다. 유효한 값에 대 한 `options` 은 다음과 같습니다.  
  
-   **/?** 또는 **/help,** 도움말 메시지를 표시 합니다.  
  
-   **/noreset 정리한,** 런타임 데이터 구조에서의 개수를 유지 합니다.  
  
 `image`  
 컴파일러 옵션 /ltcg: pginstrument를 사용 하 여 생성 된.exe 또는.dll 파일의 전체 경로입니다.  
  
 `pgcfile`  
 이 명령은를 쓸 데이터 개수.pgc 파일입니다.  
  
## <a name="remarks"></a>설명  
 이 명령은 /ltcg: pginstrument 컴파일러 옵션을 사용 하 여 빌드한 프로그램에서 작동 합니다. 실행 중인 프로그램을 중단 하 고 새.pgc 파일에 프로필 데이터를 씁니다. 이 명령은 기본적으로 각 쓰기 작업 후 카운트를 다시 설정 합니다. 지정 하는 경우는 **/noreset 정리한** 옵션을 명령 값을 기록 하지만 실행 중인 프로그램에서 다시 설정 되지 됩니다. 이 옵션을 제공 합니다 중복 데이터가 나중에 프로필 데이터를 검색 하는 경우.  
  
 에 대 한 또 다른 용도 `pgosweep` 런타임의 응용 프로그램의 프로필 정보를 검색 하는 것입니다. 실행 수는 예를 들어 `pgosweep` 직후 응용 프로그램을 시작 하 고 해당 파일을 삭제할 수 있습니다. 이 시작 비용과 관련 된 프로필 데이터를 삭제 합니다. 다음을 실행 하거나 `pgosweep` 응용 프로그램을 종료 하기 전에. 이제 수집 된 데이터에 런타임의 프로필 정보가 있습니다.  
  
 .Pgc 파일의 이름을 때 (`pgcfile`)는 표준 형식으로 사용할 수 있습니다 *appname! n*.pgc 합니다. 이 형식을 사용 하는 경우 컴파일러는 /ltcg: pgo 단계에서이 데이터를 찾을 수 있습니다. 표준 형식을 사용 하지 않는 경우 사용 해야 [pgomgr](../../build/reference/pgomgr.md) .pgc 파일을 병합 합니다.  
  
## <a name="example"></a>예  
  
```  
pgosweep myapp.exe myapp!1.pgc  
```  
  
 이 예제에서는 `pgosweep` myapp!1.pgc myapp.exe에 대 한 현재 프로필 정보를 씁니다.  
  
## <a name="see-also"></a>참고 항목  
 [수동 프로필 기반 최적화 도구](../../build/reference/tools-for-manual-profile-guided-optimization.md)