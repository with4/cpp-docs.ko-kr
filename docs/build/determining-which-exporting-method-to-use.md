---
title: 사용 하 여 사용할 내보내기 방법 결정 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- __declspec(dllexport) keyword [C++]
- exporting DLLs [C++], method comparison
- def files [C++], exporting from DLLs
- .def files [C++], exporting from DLLs
ms.assetid: 66d773ed-935c-45c2-ad03-1a060874b34d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 03c88cee3504d8efef8f9ca19073ed06b66f6aeb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="determining-which-exporting-method-to-use"></a>사용할 내보내기 방법 결정
두 가지 방법 중 하나에 함수를 내보낼 수-.def 파일 또는 `__declspec(dllexport)` 키워드입니다. 어떤 방식으로 사용 하는 것이 DLL에 대 한 더 나은 결정을 하려면 이러한 질문을 고려 합니다.  
  
-   나중에 다른 함수를 내보내려면 계획 입니까?  
  
-   프로그램 DLL을 다시 작성할 수 있습니다 또는 다시 빌드할 수 없는 응용 프로그램에서 사용 되는 응용 프로그램 에서만 사용-예를 들어 만들어진 응용 프로그램을 제 3 자에서?  
  
## <a name="pros-and-cons-of-using-def-files"></a>.Def 파일을 사용 하 여의 장점 및 단점  
 함수 내보내기 서 수를 제어 하는.def 파일 제공에 내보내는 중입니다. DLL에는 내보낸된 함수를 추가 하는 경우 다른 내보낸된 함수 보다 더 높은 서 수 값을 할당할 수 있습니다. 이 작업을 수행 암시적 연결을 사용 하는 응용 프로그램 새 함수를 포함 하는 가져오기 라이브러리에 다시 연결할 필요가 없습니다. 이 기능은 디자인 하는 경우 사용할 DLL을 많은 응용 프로그램에서 있습니다 수 새 기능을 추가 하 고 이미 의존 하는 응용 프로그램에서 제대로 작동 하려면 계속 되도록 하기 때문에 매우 편리 합니다. 예를 들어, MFC Dll.def 파일을 사용 하 여 작성 됩니다.  
  
 .Def 파일을 사용 하는 또 다른 이점은 사용할 수 있는 `NONAME` 함수를 내보내려면 특성입니다. 서 수만 DLL에서 내보내기 테이블에 추가합니다. 사용 하 여 많은 수의 내보낸된 함수를 갖고 있는 Dll에 대 한는 `NONAME` 특성 DLL 파일의 크기를 줄일 수 있습니다. 모듈 정의 문을 작성 하는 방법에 대 한 정보를 참조 하십시오. [모듈 정의 문의 규칙](../build/reference/rules-for-module-definition-statements.md)합니다. 서 수 내보내기에 대 한 정보를 참조 하십시오. [이름 대신 서 수를 사용 하 여 DLL에서 함수 내보내기](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)합니다.  
  
 .Def 파일을 사용 하 여의 단점은는 c + + 파일에서 함수를 내보내는 경우 사용자는.def에 데코레이팅된 이름을를 지정 해야 하거나 파일 또는 수행 되는 이름 데코레이션이 방지 하려면 extern "C"를 사용 하 여 내보낸된 함수를 정의 합니다. Visual c + + 컴파일러에 의해 합니다.  
  
 .Def 파일의 데코레이팅된 이름을 배치 하는 경우 사용 하 여 가져올 수 있습니다는 [DUMPBIN](../build/reference/dumpbin-reference.md) 도구 또는 링커를 사용 하 여 [/맵](../build/reference/map-generate-mapfile.md) 옵션입니다. 컴파일러에 의해 생성 되는 데코레이팅된 이름은 컴파일러로 적용 됩니다. 따라서 데코레이팅된 이름이.def 파일에는 컴파일러에 의해 생성 되는 배치 하면 DLL에 연결 하는 응용 프로그램 빌드해야와 일치 하도록 호출 응용 프로그램의 데코레이팅된 이름을 내보내는 동일한 버전의 컴파일러를 사용 하 여 i 이름 n DLL의.def 파일입니다.  
  
## <a name="pros-and-cons-of-using-declspecdllexport"></a>__Declspec (dllexport)를 사용 하 여의 장점 및 단점  
 사용 하 여 `__declspec(dllexport)` .def 파일을 유지 하 고 데코레이팅된 이름을 내보내는 함수 가져오기에 대해 걱정 하지 않아도 되므로 편리 합니다. 그러나 이러한 방식으로 내보내기의 유용성은 개수를 다시 작성 하려면 하는 연결 된 응용 프로그램에 의해 제한 됩니다. 새 내보내기로 DLL을 다시 작성 하는 경우 서로 다른 버전의 컴파일러를 사용 하 여 다시 작성 하는 경우 내보낸된 c + + 함수에 대 한 데코레이팅된 이름을 변경 될 수 있으므로 응용 프로그램을 다시 작성 해야 수도 있습니다.  
  
### <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.  
  
-   [사용 하 여 DLL에서 내보냅니다. DEF 파일](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [__Declspec (dllexport)를 사용 하 여 DLL에서 내보내기](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [AFX_EXT_CLASS를 사용 하 여 가져오기 및 내보내기](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [C 언어 실행 파일에서 사용 하기 위해 c + + 함수 내보내기](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [C 또는 c + + 언어 실행 파일에서 사용 하기 위해 내보내기 C 함수](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [__Declspec (dllimport)을 사용 하 여 응용 프로그램으로 가져오기](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [DLL 초기화](../build/run-time-library-behavior.md#initializing-a-dll)  
  
### <a name="what-do-you-want-to-know-more-about"></a>추가 정보  
  
-   [가져오기 및 내보내기 인라인 함수](../build/importing-and-exporting-inline-functions.md)  
  
-   [상호 가져오기](../build/mutual-imports.md)  
  
-   [데코레이팅된 이름](../build/reference/decorated-names.md)  
  
## <a name="see-also"></a>참고 항목  
 [DLL에서 내보내기](../build/exporting-from-a-dll.md)