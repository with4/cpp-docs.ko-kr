---
title: "pgosweep | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pgosweep 프로그램"
  - "프로필 기반 최적화, pgosweep"
ms.assetid: f39dd3b7-1cd9-4c3b-8e8b-fb794744b757
caps.latest.revision: 22
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# pgosweep
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

프로필 기반 최적화 시 실행 중인 프로그램의 모든 프로필 데이터를 .pgc 파일에 쓰는 데 사용됩니다.  
  
## 구문  
  
```  
pgosweep [options] image pgcfile  
```  
  
#### 매개 변수  
 `options`  
 선택적 매개 변수로, 공백으로 두어도 됩니다.  `options`에 사용할 수 있는 값은 다음과 같습니다.  
  
-   **\/?** 또는 **\/help,**  \- 이 도움말 메시지를 표시합니다.  
  
-   **\/noreset,** \- 런타임 데이터 구조에서 카운트를 유지합니다.  
  
 `image`  
 컴파일러 옵션 \/LTCG:PGINSTRUMENT를 사용하여 만든 .exe 또는 .dll 파일의 전체 경로입니다.  
  
 `pgcfile`  
 이 명령으로 데이터 카운트를 쓸 .pgc 파일입니다.  
  
## 설명  
 이 명령은 컴파일러 옵션 \/LTCG:PGINSTRUMENT를 사용하여 빌드된 프로그램에 사용할 수 있습니다.  이 명령은 실행 중인 프로그램을 중단하고 프로필 데이터를 새 .pgc 파일에 씁니다.  기본적으로 이 명령은 쓰기 작업이 끝날 때마다 카운트를 다시 설정합니다.  **\/noreset** 옵션이 지정된 경우에는 카운트 값을 기록하기만 하고 실행 중인 프로그램에서 다시 설정하지는 않습니다.  이 옵션을 사용하면 나중에 프로필 데이터를 검색할 경우 중복 데이터를 얻게 됩니다.  
  
 `pgosweep`의 또 다른 용도는 응용 프로그램 런타임의 프로필 정보만 검색하는 것입니다.  예를 들어 응용 프로그램을 시작한 직후에 `pgosweep`을 실행하고 해당 파일을 삭제할 수 있습니다.  이렇게 하면 시작 비용과 관련된 프로필 데이터가 제거됩니다.  그런 다음 응용 프로그램을 끝내기 전에 `pgosweep`을 실행할 수 있습니다.  그러면 수집된 데이터에는 런타임의 프로필 정보만 포함됩니다.  
  
 .pgc 파일의 이름을 지정할 때\(`pgcfile`\) 표준 형식인 *appname\!n*.pgc를 사용할 수 있습니다.  이 형식을 사용하면 컴파일러에서는 \/LTCG:PGO 단계에서 이 데이터를 찾습니다.  표준 형식을 사용하지 않는 경우에는 [pgomgr](../../build/reference/pgomgr.md)를 사용하여 .pgc 파일을 병합해야 합니다.  
  
## 예제  
  
```  
pgosweep myapp.exe myapp!1.pgc  
```  
  
 이 예제에서 `pgosweep`은 myapp.exe에 대한 현재 프로필 정보를 myapp\!1.pgc에 씁니다.  
  
## 참고 항목  
 [프로필 기반 최적화 도구](../../build/reference/tools-for-manual-profile-guided-optimization.md)