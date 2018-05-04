---
title: 링커의 지연 로드 된 Dll 지원 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- delayed loading of DLLs, linker support
ms.assetid: b2d7e449-2809-42b1-9c90-2c0ca5e31a14
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aea4ca6d5391f71f27d59d0192fcf1f832dd6702
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="linker-support-for-delay-loaded-dlls"></a>링커의 지연 로드된 DLL 지원
이제 Visual c + + 링커는 Dll의 지연된 로드를 지원합니다. 이 방식으로 제공 절약 Windows SDK 함수를 사용할 필요가 **LoadLibrary** 및 **GetProcAddress** DLL 지연 로드를 구현 하 합니다.  
  
 이전 Visual c + + 6.0 실행 시 DLL을 로드 하는 유일한 방법은 사용 했습니다 **LoadLibrary** 및 **GetProcAddress**; 운영 체제 DLL을 로드 하면 실행 파일 또는 로드 된 DLL를 사용 하 여 합니다.  
  
 Visual c + + 6.0 부터는 DLL에 정적으로 링크 하는 경우 링커는 프로그램이 해당 DLL의 함수를 호출할 때까지 지연 하는 옵션이 DLL을 로드할 제공 합니다.  
  
 응용 프로그램을 지연 시킬 수 사용 하 여 DLL 로드는 [/DELAYLOAD (가져오기 로드 지연)](../../build/reference/delayload-delay-load-import.md) 링커 옵션을 도우미 함수 (Visual c + +에서 제공 되는 기본 구현)입니다. 도우미 함수를 호출 하 여 런타임 시 DLL을 로드할 됩니다 **LoadLibrary** 및 **GetProcAddress** 드립니다.  
  
 지연 DLL 로드 하는 경우 고려해 야 합니다.  
  
-   프로그램은 DLL의 함수를 호출할 수 있습니다.  
  
-   프로그램 실행 후반부에 DLL의 함수를 호출 될 수 있습니다.  
  
 DLL의 지연된 로드의 빌드 중 지정할 수는 있습니다. EXE 또는 합니다. DLL 프로젝트입니다. A입니다. 하나 이상의 Dll의 로드를 지연 시키는 DLL 프로젝트 호출 해서는 안 자체 지연 로드 된 진입점 Dllmain에 있습니다.  
  
 다음 항목에서는 Dll의 지연 로드:  
  
-   [지연 로드할 DLL 지정](../../build/reference/specifying-dlls-to-delay-load.md)  
  
-   [지연 로드된 DLL의 명시적 언로드](../../build/reference/explicitly-unloading-a-delay-loaded-dll.md)  
  
-   [지연 로드된 DLL에 대한 모든 가져오기 로드](../../build/reference/loading-all-imports-for-a-delay-loaded-dll.md)  
  
-   [가져오기 바인딩](../../build/reference/binding-imports.md)  
  
-   [오류 처리 및 알림](../../build/reference/error-handling-and-notification.md)  
  
-   [지연 로드된 가져오기 덤프](../../build/reference/dumping-delay-loaded-imports.md)  
  
-   [DLL 지연 로드의 제약 조건](../../build/reference/constraints-of-delay-loading-dlls.md)  
  
-   [도우미 함수 이해](understanding-the-helper-function.md)  
  
-   [사용자 도우미 함수 개발](../../build/reference/developing-your-own-helper-function.md)  
  
## <a name="see-also"></a>참고 항목  
 [Visual c + +의 Dll](../../build/dlls-in-visual-cpp.md)   
 [링크](../../build/reference/linking.md)