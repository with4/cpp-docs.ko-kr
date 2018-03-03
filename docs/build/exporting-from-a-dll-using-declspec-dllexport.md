---
title: "__Declspec (dllexport)를 사용 하 여 DLL에서 내보내기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- dllexport
- __declspec
dev_langs:
- C++
helpviewer_keywords:
- __declspec(dllexport) keyword [C++]
- names [C++], DLL exports by
- export directives [C++]
- exporting DLLs [C++], __declspec(dllexport) keyword
ms.assetid: a35e25e8-7263-4a04-bad4-00b284458679
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 51f20e47724a6d32dad014fbaf025cd283112c54
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="exporting-from-a-dll-using-declspecdllexport"></a>__declspec(dllexport)을 사용하여 DLL에서 내보내기
도입 된 Microsoft **__export** 16 비트 컴파일러 버전의 Visual c + + 컴파일러가 내보내기 이름을 자동으로 생성 하는.lib 파일에 배치할 수 있도록 합니다. 이.lib 파일은 DLL에 연결 하는 정적.lib 처럼 방금 사용할 수 있습니다.  
  
 새 컴파일러 버전에서는 내보낼 수 있습니다 데이터, 함수, 클래스 또는 클래스 멤버 함수에서 사용 하 여 DLL에서 **__declspec (dllexport)** 키워드입니다. **__declspec (dllexport)** 되므로.def 파일을 사용 하지 않고도 내보내기 지시문을 개체 파일을 추가 합니다.  
  
 이 편의 데코 레이트 된 c + + 함수 이름 내보낼 때 특히 합니다. 이름 데코레이션에 대 한 지정이 없는 표준 이기 때문에 내보낸 함수의 이름이 컴파일러 버전 간에 변경 될 수 있습니다. 사용 하는 경우 **__declspec (dllexport)**, DLL 및 종속.exe 파일은 다시 컴파일합니다에 대 한 계정에만 필요 합니다.  
  
 많은 내보내기 지시문와 같은 서 수, NONAME, 및 PRIVATE.def 파일에만 구성할 수 있으며.def 파일 없이 이러한 특성을 지정할 수 없습니다. 그러나를 사용 하 여 **__declspec (dllexport)** 는.def를 사용 하 여 파일 빌드 오류가 발생 하지 않습니다.  
  
 함수를 내보내려면는 **__declspec (dllexport)** 키워드는 키워드를 지정 하는 경우 호출 규칙 키워드의 왼쪽에 나타나야 합니다. 예:  
  
```  
__declspec(dllexport) void __cdecl Function1(void);  
```  
  
 모든 공용 데이터 멤버 및 클래스의 멤버 함수를 내보내려면 키워드 해야 클래스 이름의 왼쪽에 다음과 같이 나타납니다.  
  
```  
class __declspec(dllexport) CExampleExport : public CObject  
{ ... class definition ... };  
```  
  
> [!NOTE]
>  `__declspec(dllexport)`사용 하는 함수에 적용할 수 없습니다는 `__clrcall` 호출 규칙입니다.  
  
 함수 프로토타입 및/또는 내보내는 하 고 추가 클래스를 포함 하는 헤더 파일 DLL을 빌드할 때 일반적으로 만들고 **__declspec (dllexport)** 헤더 파일에 선언에 있습니다. 코드를 더 읽기 쉽게 하려면에 대 한 매크로 정의 **__declspec (dllexport)** 내보내는 각 기호로 매크로 사용 합니다.  
  
```  
#define DllExport   __declspec( dllexport )   
```  
  
 **__declspec (dllexport)** 저장소 함수는 DLL의 내보내기 테이블의 이름입니다. 참조 테이블의 크기를 최적화 하려면 [이름 대신 서 수를 사용 하 여 DLL에서 함수 내보내기](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md)합니다.  
  
> [!NOTE]
>  W i n 32에서 Win16 DLL 소스 코드를 이식 하는 경우 각 인스턴스의 바꿉니다 **__export** 와 **__declspec (dllexport)**합니다.  
  
 참조로 Win32 Winbase.h 헤더 파일에서 검색 합니다. 예제가 포함 되어 **__declspec (dllimport)** 사용 합니다.  
  
## <a name="what-do-you-want-to-do"></a>원하는 작업을 선택하세요.  
  
-   [.Def 파일을 사용 하 여 DLL에서 내보내기](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [AFX_EXT_CLASS를 사용 하 여 가져오기 및 내보내기](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [C 언어 실행 파일에서 사용 하기 위해 c + + 함수 내보내기](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [C 또는 c + + 언어 실행 파일에서 사용 하기 위해 내보내기 C 함수](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [사용할 내보내기 방법 결정](../build/determining-which-exporting-method-to-use.md)  
  
-   [__Declspec (dllimport)을 사용 하 여 응용 프로그램으로 가져오기](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [DLL 초기화](../build/run-time-library-behavior.md#initializing-a-dll)  
  
## <a name="what-do-you-want-to-know-more-about"></a>추가 정보  
  
-   [__Declspec 키워드](../cpp/declspec.md)  
  
-   [가져오기 및 내보내기 인라인 함수](../build/importing-and-exporting-inline-functions.md)  
  
-   [상호 가져오기](../build/mutual-imports.md)  
  
## <a name="see-also"></a>참고 항목  
 [DLL에서 내보내기](../build/exporting-from-a-dll.md)