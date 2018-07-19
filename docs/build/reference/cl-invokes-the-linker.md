---
title: CL에서의 링커 호출 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- cl
dev_langs:
- C++
helpviewer_keywords:
- compiling source code [C++], without linking
- invoking linker from the compiler
- LINK tool [C++], invoking from CL compiler
- cl.exe compiler [C++], compiling without linking
- cl.exe compiler [C++], controlling linker
ms.assetid: eae47ef7-09eb-40c9-b318-7c714cd452fc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bc9c5c4815dc83b37d0b7971d5fd0f31db51e39e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32371917"
---
# <a name="cl-invokes-the-linker"></a>CL에서의 링커 호출
CL /c 옵션을 사용 하지 않으면 컴파일한 다음 링커를 자동으로 호출 합니다. CL 컴파일하는 동안 만들어진.obj 파일의 이름 및 명령줄에 지정 된 다른 파일의 이름이 링커로 전달 합니다. 링커가 링크 환경 변수에 나열 된 옵션을 사용 합니다. CL 명령줄에서 링커 옵션을 지정 하려면 /link 옵션을 사용할 수 있습니다. /Link 옵션을 다음 옵션을 LINK 환경 변수를 재정의 합니다. 다음 표의 옵션 링크 하지 않도록 합니다.  
  
|옵션|설명|  
|------------|-----------------|  
|/c|링크 하지 않고 컴파일|  
|/ E, /EP /P|링크 하지 않고 전처리|  
|/Zg|함수 프로토타입 생성|  
|/Zs|구문 검사|  
  
 연결에 대 한 자세한 내용은 참조 하십시오. [링커 옵션](../../build/reference/linker-options.md)합니다.  
  
## <a name="example"></a>예제  
 세 가지 C 소스 파일을 컴파일하는 것으로 가정: MAIN.c 및 MOD1.c와 MOD2.c 합니다. 각 파일에 다른 파일에 정의 된 함수에 대 한 호출에 포함 됩니다.  
  
-   함수를 호출 하는 MAIN.c `func1` MOD1.c 및 함수에 `func2` MOD2.c에 합니다.  
  
-   표준 라이브러리 함수를 호출 하는 MOD1.c `printf_s` 및 `scanf_s`합니다.  
  
-   MOD2.c 이라는 그래픽 함수를 호출 `myline` 및 `mycircle`, 합니다에 정의 된입니다.  
  
 이 프로그램을 작성 하려면 다음 명령줄에서 컴파일하십시오.  
  
```  
CL MAIN.c MOD1.C MOD2.C MYGRAPH.lib  
```  
  
 CL C 소스 파일 먼저 컴파일하고 MAIN.obj, MOD1.obj 및 MOD2.obj 개체 파일을 만듭니다. 컴파일러는 각.obj 파일에 표준 라이브러리의 이름을 배치합니다. 자세한 내용은 참조 하십시오. [런타임 라이브러리 사용](../../build/reference/md-mt-ld-use-run-time-library.md)합니다.  
  
 CL은 링커에 합니다, 이름과 함께.obj 파일의 이름을 전달 합니다. 링커가 외부 참조를 다음과 같이 해결 됩니다.  
  
1.  MAIN.obj에 대 한 참조에서에서 `func1` MOD1.obj; 정의 사용 하 여 확인이에 대 한 참조 `func2` MOD2.obj 정의 사용 하 여 확인 됩니다.  
  
2.  에 대 한 참조 MOD1.obj에서 `printf_s` 및 `scanf_s` MOD1.obj 내 라는 링커 발견 하는 라이브러리의 정의 사용 하 여 확인 됩니다.  
  
3.  MOD2.obj에 대 한 참조에서에서 `myline` 및 `mycircle` 합니다의 정의 사용 하 여 확인 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [컴파일러 옵션](../../build/reference/compiler-options.md)   
 [컴파일러 옵션 설정](../../build/reference/setting-compiler-options.md)