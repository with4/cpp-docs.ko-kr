---
title: "디스크에 커밋 상수 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.constants"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "디스크에 커밋 상수"
ms.assetid: 0b903b23-b4fa-431e-a937-51d95f695ecf
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 디스크에 커밋 상수
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 전용**  
  
## 구문  
  
```  
  
#include <stdio.h>  
```  
  
## 설명  
 이러한 마이크로 소프트 고유의 상수는 열려있는 파일과 관련된 버퍼가 운영 시스템 버퍼 또는 디스크에 플러시되는지 여부를 지정합니다.  모드는 읽기\/쓰기 액세스 유형을 지정 하는 문자열에 포함 됩니다. \(**"r"**, **"w"**, **"a"**, **"r\+"**, **"w\+"**, **"a\+"**\).  
  
 디스크에 커밋 모드는 다음과 같습니다.  
  
 **c**  
 지정된 버퍼의 기록되지 않은 내용을 디스크에 씁니다.  이 커밋 디스크에 저장하는 기능은 [fflush](../c-runtime-library/reference/fflush.md)를하거나 [\_flushall](../c-runtime-library/reference/flushall.md) 기능 중 하나를 명시적으로 호출할 때 발생합니다.  이 모드는 중요한 데이터를 처리할 때 유용 합니다.  예를 들어, 프로그램이 `fflush` 또는 `_flushall` 를 호출한 후에 종료 된 경우, 사용자의 데이터가 운영 체제의 버퍼에 도달한 것을 확인할 수 있습니다.  그러나 **c** 옵션을 사용하여 파일이 열리지 않는 한, 운영 체제가 또한 종료되지 않는 경우 데이터는 디스크에 쓰이지 않습니다.  
  
 **n**  
 지정된 된 버퍼의 내용을 기록 되지 않은 운영 체제 버퍼에 씁니다.  운영 체제는 데이터를 캐시 한 후 디스크에 기록 할 수있는 최적의 시간을 결정합니다.  많은 상황에서,이 동작은 효율적인 프로그램 동작을 만듭니다.  데이터의 보존 \(예 : 은행 거래나 항공권 정보 등\) 중요한 경우, **c** 옵션을 사용하는 것이 좋습니다.  **n** 모드는 기본입니다.  
  
> [!NOTE]
>  **c** 및 **n** 옵션은 `fopen` 에 대한 ANSI 표준에 포함되어 있지 않습니다. 그러나 Microsoft는 확장 및 ANSI 이식성이 필요한 곳에 사용되지 않습니다.  
  
## 기존 코드를 사용 하여 디스크에 커밋 기능을 사용합니다.  
 기본적으로 [fflush](../c-runtime-library/reference/fflush.md) 또는 [\_flushall](../c-runtime-library/reference/flushall.md) 라이브러리 함수에 대한 호출은 데이터를 운영 체제에 의해 관리 되는 버퍼에 씁니다.  운영 체제가 실제로 디스크에 데이터를 기록 할 수있는 최적의 시간을 결정합니다.  런타임 라이브러리의 커밋 디스크에 저장하는 기능을 사용하면 중요한 데이터가 운영 체제의 버퍼에 대신 디스크에 직접 기록되어 있는지 확인 할 수 있습니다.  COMMODE.OBJ 사용 하여 개체 파일을 연결 하여 다시 작성 하지 않고 기존 프로그램에 이 기능을 제공할 수 있습니다.  
  
 실행 파일의 결과에서, `fflush` 에 대한 호출은 버퍼의 내용을 디스크에 직접쓰고 `_flushall` 에 대한 호출은 모든 버퍼의 내용을 디스크에 씁니다.  이 두 기능은 COMMODE.OBJ에 의해 영향을 받습니다.  
  
 **Microsoft 전용 종료**  
  
## 참고 항목  
 [스트림 I\/O](../c-runtime-library/stream-i-o.md)   
 [\_fdopen, \_wfdopen](../c-runtime-library/reference/fdopen-wfdopen.md)   
 [fopen, \_wfopen](../c-runtime-library/reference/fopen-wfopen.md)   
 [전역 상수](../c-runtime-library/global-constants.md)