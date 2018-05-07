---
title: 링커 도구 경고 LNK4210 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4210
dev_langs:
- C++
helpviewer_keywords:
- LNK4210
ms.assetid: db48cff8-a2be-4a77-8d03-552b42c228fa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d2bd34866264fdfea71ba7496ad9c94446fd5726
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4210"></a>링커 도구 경고 LNK4210  
  
> 섹션 *섹션* 존재; 있을 수 있습니다 수 처리 되지 않은 정적 이니셜라이저 또는 종결자  
  
일부 코드에 정적 이니셜라이저 또는 종결자를 도입 하지만 VCRuntime 라이브러리 시작 코드 또는 (정적 이니셜라이저 또는 종결자를 실행 해야 함)는 해당 하는 응용 프로그램이 시작 될 때 실행 되지 않습니다. 정적 이니셜라이저 또는 종결자를 필요로 하는 코드의 몇 가지 예는 다음과 같습니다.  
  
-   생성자, 소멸자 또는 가상 함수 테이블 변수는 전역 클래스입니다.  
  
-   전역 변수는 비 컴파일 시간 상수를 사용 하 여 초기화 합니다.  
  
이 문제를 해결 하려면 다음 중 하나를 시도해 보십시오.  
  
-   정적 이니셜라이저가 있는 모든 코드를 제거 합니다.  
  
-   사용 하지 마십시오 [/NOENTRY](../../build/reference/noentry-no-entry-point.md)합니다. /NOENTRY를 제거한 후 제거 해야 또한 [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) 링커 명령줄의 합니다.  
  
-   빌드 /MT을 사용 하는 경우 libcmt.lib, libvcruntime.lib 및 libucrt.lib 링커 명령줄에 추가 합니다. 빌드 /MTd를 사용할 경우 libcmtd.lib, vcruntimed.lib, 및 libucrtd.lib를 추가 합니다.  
  
-   /Clr에서 이동할 때: /clr 컴파일에 순수 제거는 [/ENTRY](../../build/reference/entry-entry-point-symbol.md) 링커 줄에서 옵션입니다. CRT 초기화 있으며 정적 이니셜라이저 응용 프로그램 시작 시 실행 되도록 허용 합니다.  
  
 [/GS](../../build/reference/gs-buffer-security-check.md) 컴파일러 옵션을 사용 하 여 초기화 하려면는 `__security_init_cookie` 함수입니다. 이 초기화에서 실행 되는 VCRuntime 라이브러리 시작 코드에는 기본적으로 제공 됩니다 `_DllMainCRTStartup`합니다.  
  
-   /ENTRY를 사용 하 여 프로젝트를 빌드하고 및 /ENTRY 전달 되는 경우 함수가 아닌 다른 `_DllMainCRTStartup`, 함수를 호출 해야 `_CRT_INIT` CRT를 초기화 합니다. DLL /GS를 사용 하 여 정적 이니셜라이저 등이 필요 하거나 MFC 또는 ATL 코드의 컨텍스트 내에서 호출할 경우이 호출은 만으로는 충분 하지 않습니다. 참조 [Dll 및 Visual c + + 런타임 라이브러리 동작](../../build/run-time-library-behavior.md) 자세한 정보에 대 한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [링커 옵션 설정](../../build/reference/setting-linker-options.md)