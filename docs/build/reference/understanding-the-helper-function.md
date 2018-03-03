---
title: "도우미 함수 이해 | Microsoft Docs"
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
- delayed loading of DLLs, helper function
- __delayLoadHelper2 function
- delayimp.lib
- __delayLoadHelper function
- delayhlp.cpp
- delayimp.h
- helper functions
ms.assetid: 6279c12c-d908-4967-b0b3-cabfc3e91d3d
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c3a013cf584c37f84331a5ab5dfe74eaa213c851
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="understanding-the-helper-function"></a>도우미 함수 이해
지연된 로드 링커 지원에 대 한 도우미 함수는 실제로 실행 시 DLL을 로드 합니다. 사용자 고유의 함수를 작성 Delayimp.lib에 제공 된 도우미 함수를 사용 하는 대신 프로그램에 연결 하 여 동작을 사용자 지정할 도우미 함수를 수정할 수 있습니다. 한 도우미 함수는 모든 지연 로드 된 Dll을 지원합니다.  
  
 DLL 이나 가져오기의 이름을 기반으로 하는 특정 처리를 수행 하려는 경우 고유한 버전의 도우미 함수를 제공할 수 있습니다.  
  
 도우미 함수는 다음 작업을 수행합니다.  
  
-   이미 로드 했습니다가 확인 하려면 라이브러리에 저장 된 핸들을 확인 합니다.  
  
-   호출 **LoadLibrary** DLL의 로드를 시도 합니다.  
  
-   호출 **GetProcAddress** 프로시저의 주소를 시도 하려면  
  
-   현재 로드 된 진입점을 호출 하는 썽크를 로드 하는 지연 가져오기로 반환  
  
 도우미 함수는 다음과 같은 작업 한 후 프로그램에서 알림 후크로 다시 호출할 수 있습니다.:  
  
-   도우미 함수 시작 될 때  
  
-   바로 전에 **LoadLibrary** 도우미 함수에서 호출  
  
-   바로 전에 **GetProcAddress** 도우미 함수에서 호출  
  
-   경우에 대 한 호출 **LoadLibrary** 도우미 함수에 실패 했습니다.  
  
-   경우에 대 한 호출 **GetProcAddress** 도우미 함수에 실패 했습니다.  
  
-   함수가 완료 되는 도우미 후 처리  
  
 이러한 각 연결 포인트 지연 가져오기 부하 썽크 돌아가기 제외한 어떤 식으로든 도우미 루틴의 정상 프로세스에서 변경 하는 값을 반환할 수 있습니다.  
  
 기본 도우미 코드 Delayhlp.cpp 및 Delayimp.h (vc\include)에서 찾을 수 있으며 (vc\lib)에서 Delayimp.lib에 컴파일됩니다. 사용자 도우미 함수를 작성 하지 않는 경우이 라이브러리에 컴파일에 포함 해야 합니다.  
  
 도우미 함수를 다음과 같습니다.  
  
-   [Visual C++ 6.0 이후 DLL 지연 로드 도우미 함수의 변경 내용](../../build/reference/changes-in-the-dll-delayed-loading-helper-function-since-visual-cpp-6-0.md)  
  
-   [호출 규칙, 매개 변수, 반환 형식](../../build/reference/calling-conventions-parameters-and-return-type.md)  
  
-   [구조체 및 상수 정의](../../build/reference/structure-and-constant-definitions.md)  
  
-   [필요한 값 계산](../../build/reference/calculating-necessary-values.md)  
  
-   [지연 로드된 DLL 언로드](../../build/reference/explicitly-unloading-a-delay-loaded-dll.md)  
  
## <a name="see-also"></a>참고 항목  
 [링커의 지연 로드된 DLL 지원](../../build/reference/linker-support-for-delay-loaded-dlls.md)