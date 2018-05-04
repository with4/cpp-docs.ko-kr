---
title: DLL에 실행 파일 링크 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- run time [C++], linking
- dynamic load linking [C++]
- linking [C++], DLLs
- DLLs [C++], linking
- implicit linking [C++]
- explicit linking [C++]
- executable files [C++], linking to DLLs
- loading DLLs [C++]
ms.assetid: 7592e276-dd6e-4a74-90c8-e1ee35598ea3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4f1f8c329d8b2ba6ddedacca626a2b386e499671
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="link-an-executable-to-a-dll"></a>DLL에 실행 파일 링크  
  
실행 파일에 연결 (또는 로드) DLL의 두 가지 방법 중 하나:  
  
-   *암시적 링크*, 사용 하 여 실행 파일이 로드 될 때 운영 체제는 DLL을 로드 하는 위치입니다. 클라이언트 실행 한 경우 처럼 함수 된 정적으로 연결 하 고 실행 파일 내에 포함 된 DLL의 내보낸된 함수를 호출 합니다. 암시적 링크 때때로 이라고 *정적 로드* 또는 *로드 시간 동적 연결*합니다.  
  
-   *명시적 링크*, 운영 체제 런타임에 필요에 따라 DLL을 로드 합니다. 명시적 연결 하 여 DLL을 사용 하는 실행 파일이 DLL에서 내보낸 함수에 액세스 하 고 명시적으로 로드 하 고 DLL을 언로드 함수 호출을 확인 해야 합니다. 정적으로 연결 된 라이브러리의 함수에 대 한 호출을 달리 클라이언트 실행 파일은 DLL 함수 포인터를 통해 내보낸된 함수를 호출 해야 합니다. 명시적 링크 때때로 이라고 *동적 부하* 또는 *런타임에 동적 링크*합니다.  
  
실행 파일 링크 방법 중 하나를 사용 동일한 DLL에 연결할 수 있습니다. 이러한 메서드는 함께 사용할 수 없습니다; 또한 하나의 실행 암시적으로 DLL에 연결 하 고 다른 인스턴스에 연결할 수 명시적으로 합니다.  
  
<a name="determining-which-linking-method-to-use"></a>  
  
## <a name="determine-which-linking-method-to-use"></a>사용할 연결 방법을 결정 합니다.  
  
암시적 링크 또는 명시적 링크 사용 여부는 응용 프로그램에 대해 수행 해야 하는 아키텍처 결정입니다. 각 메서드에 장단점이 있습니다.  
  
### <a name="implicit-linking"></a>암시적 링크  
  
암시적 링크 응용 프로그램의 코드에서 내보낸된 DLL 함수를 호출할 때 발생 합니다. 호출 실행에 대 한 소스 코드 컴파일 또는 조합 된 경우 DLL 함수 호출 개체 코드에서 외부 함수 참조를 생성 합니다. 이 외부 참조를 해결 하려면 응용 프로그램 DLL의 작성자가 제공 하는 가져오기 라이브러리 (.lib 파일)에 연결 해야 합니다.  
  
가져오기 라이브러리 DLL을 로드 하 고 DLL에서 함수 호출을 구현 하는 코드가 포함 됩니다. 가져오기 라이브러리에는 외부 함수 DLL에서 해당 함수에 대 한 코드를 사실이 링커에 전달 합니다. Dll에 대 한 외부 참조를 해결 하려면 링커 프로세스가 시작 될 때 DLL 코드를 찾을 수 있는 위치를 시스템에 알려주는 실행 파일에 정보 단순히 추가 합니다.  
  
시스템 동적으로 연결 된 참조를 포함 하는 프로그램을 시작할 때 정보를 사용 프로그램의 실행 파일에 필요한 Dll을 찾습니다. DLL을 찾을 수 없는 시스템 프로세스를 종료 하 고 오류를 보고 하는 대화 상자를 표시 합니다. 그렇지 않으면 시스템 프로세스의 주소 공간에 DLL 모듈을 매핑합니다.  
  
있는 경우 가입는 Dll의 초기화 및 종료 코드에 대 한 진입점 함수 같은 `DllMain`, 운영 체제 함수를 호출 합니다. 이 프로세스에 연결 된 DLL을 나타내는 코드 진입점 함수에 전달 된 매개 변수 중 하나를 지정 합니다. 진입점 함수가 TRUE를 반환 하지 않는 경우 시스템에서 프로세스를 종료 하 고 오류를 보고 합니다.  
  
마지막으로, 시스템 시작 주소 DLL 함수를 제공 하는 프로세스의 실행 코드를 수정 합니다.  
  
프로그램의 코드의 나머지 부분에서는 같은 프로세스 시작 되 고 필요한 경우에 메모리에 로드 될 때 DLL 코드 프로세스의 주소 공간에 매핑됩니다. 결과적으로 `PRELOAD` 및 `LOADONCALL` .def 파일을 더 이상 이전 버전의 Windows 로드 하는 제어에서 사용 하는 코드 특성 의미를 갖습니다.  
  
### <a name="explicit-linking"></a>명시적 링크  
  
대부분의 응용 프로그램 사용 하기 쉬운 링크 방법 이기 때문에 암시적 링크를 사용 합니다. 그러나 명시적 링크이 필요한 경우가 있습니다. 명시적 링크를 사용 하는 몇 가지 일반적인 이유는 다음과 같습니다.  
  
-   응용 프로그램 런타임이 될 때까지 로드 된 DLL의 이름을 알 수 없습니다. 예를 들어 응용 프로그램 시작 시 구성 파일에서 DLL 이름과 내보낸된 함수를 가져올 수 있습니다.  
  
-   암시적 링크를 사용 하는 프로세스는 프로세스를 시작할 때 DLL은 찾을 수 없는 경우 운영 체제에 의해 종료 됩니다. 명시적 링크를 사용 하는 프로세스가이 상황에서 종결 되지 하 고 오류에서 복구 하려고 할 수 있습니다. 예를 들어 프로세스 오류의 사용자에 게 알리는 및 DLL에 다른 경로 지정 하는 사용자 수 없습니다.  
  
-   가 연결 된 Dll 중 어느 경우에 암시적 링크를 사용 하는 프로세스 종료 되는 `DllMain` 함수에 오류가 발생 합니다. 명시적 링크를 사용 하는 프로세스가이 상황에서 종결 되지 않았습니다.  
  
-   암시적으로 여러 Dll에 링크 하는 응용 프로그램 Windows 응용 프로그램 로드 될 때 모든 Dll을 로드 하기 때문에 시작 속도가 느릴 수 있습니다. 시작 성능을 개선 하기 위해 응용 프로그램 로드, 대기 후 즉시 필요한 다른 Dll에 명시적으로 연결 하는 데 필요한 될 때까지 이러한 Dll에만 암시적으로 연결할 수 있습니다.  
  
-   명시적 링크 가져오기 라이브러리를 사용 하 여 응용 프로그램을 연결할 필요가 없습니다. 명시적 링크를 사용 하는 응용 프로그램 경우 DLL의 변경 내보내기 서 수가 변경 되 면를 호출 하는 경우 다시 연결 필요가 없으며 `GetProcAddress` 암시적 연결을 사용 하는 응용 프로그램에 다시 링크 해야 함수와 서 수 값이 아닌 이름을 사용 하는 새로운 가져오기 라이브러리입니다.  
  
다음은 주의 해야 할 명시적 링크의 두 위험입니다.  
  
-   DLL에 경우는 `DllMain` 진입점 함수를 운영 체제 함수를 호출한 스레드 컨텍스트에서 호출 `LoadLibrary`합니다. 이전 호출으로 인해 프로세스에 DLL가 이미 연결 하는 경우에 진입점 함수가 호출 되지 않습니다 `LoadLibrary` 에 대 한 해당 호출이 한가 `FreeLibrary` 함수입니다. 명시적 링크 문제가 발생할 수 있습니다는 DLL을 사용 하는 경우는 `DllMain` 함수 초기화를 수행 하는 프로세스의 각 스레드에 대 한 스레드가 이미 존재 하므로 때 `LoadLibrary` (또는 `AfxLoadLibrary`) 라고 요소가 초기화 되지 않았습니다.  
  
-   DLL에 정적 범위 데이터를 선언 하면 `__declspec(thread)`, 명시적으로 연결 되어 있는 경우 보호 오류가 발생할 수 있습니다. 호출 하 여 DLL을 로드 한 후 `LoadLibrary`,이 데이터는 코드에서 참조 될 때마다 보호 오류를 발생 시킵니다. (정적 범위 데이터는 전역 및 로컬 정적 항목이 포함 됩니다.) 따라서 DLL을 만들 때 스레드 로컬 저장소를 사용 하지 않도록 하거나 동적 DLL을 로드 하는 중 발생할 수 있는 문제점에 대 한 DLL 사용자에 게 알립니다. 자세한 내용은 참조 [스레드 로컬 저장소를 사용 하 여 동적 연결 라이브러리 (Windows SDK)에](http://msdn.microsoft.com/library/windows/desktop/ms686997)합니다.  
  
<a name="linking-implicitly"></a>  
  
## <a name="how-to-link-implicitly-to-a-dll"></a>암시적으로 DLL에 연결 하는 방법  
  
암시적 연결 하 여 DLL을 사용 하려면 클라이언트 실행 파일은 DLL의 공급자에서 이러한 파일을 구해야 합니다.  
  
-   하나 이상의 헤더 파일 (.h) 내보낸된 데이터, 함수 및/또는 c + + DLL의 클래스의 선언을 포함 하는 합니다. 클래스, 함수 및 해당 DLL에서 내보낸 데이터 모두 표시 되어야 합니다 `__declspec(dllimport)` 헤더 파일에 있습니다. 자세한 내용은 참조 [dllexport, dllimport](../cpp/dllexport-dllimport.md)합니다.  
  
-   실행 파일에 연결 하는 가져오기 라이브러리입니다. 링커는 DLL을 빌드할 때 가져오기 라이브러리를 만듭니다. 자세한 내용은 참조 [합니다. LIB 파일](../build/reference/dot-lib-files-as-linker-input.md)합니다.  
  
-   실제 DLL 파일입니다.  
  
암시적 연결 하 여 DLL을 사용 하려면 실행 파일 데이터, 함수 또는 내보낸된 데이터, 함수 및 클래스에 대 한 호출을 포함 하는 각 소스 파일에서 해당 DLL에서 내보내기 하는 c + + 클래스를 선언 하는 헤더 파일을 포함 해야 합니다. 코딩 관점에서 내보낸된 함수에 대 한 호출은 다른 함수 호출이 동일 합니다.  
  
호출 실행 파일을 빌드하려면 가져오기 라이브러리에 링크 합니다. 외부 메이크파일을 사용 하 여 시스템을 빌드할 경우에 연결 하는 라이브러리 또는 다른 개체 (.obj) 파일을 나열할 수 가져오기 라이브러리의 파일 이름을 지정 합니다.  
  
운영 체제 호출 실행을 로드할 때 DLL 파일을 찾을 수 있어야 합니다. 즉, 응용 프로그램을 배포 하거나 응용 프로그램을 설치 하는 경우 DLL의 존재 여부를 확인 해야 합니다.   
  
<a name="linking-explicitly"></a>  
  
## <a name="how-to-link-explicitly-to-a-dll"></a>명시적으로 DLL에 연결 하는 방법  
  
명시적 연결 하 여 DLL을 사용 하려면 응용 프로그램 실행 시 명시적으로 DLL을 로드 하는 함수를 확인 해야 합니다. 명시적으로 DLL에 연결, 하려면 응용 프로그램 해야 합니다.  
  
-   호출 [LoadLibrary](loadlibrary-and-afxloadlibrary.md), `LoadLibraryEx`, 또는 비슷한 기능을 DLL을 로드 하 고 모듈 핸들을 가져옵니다.  
  
-   호출 [GetProcAddress](getprocaddress.md) 내보낸 응용 프로그램을 호출 하는 함수를 각각에 대 한 함수 포인터를 가져올 수 있습니다. 포인터를 통해 DLL 함수를 호출 하는 응용 프로그램, 하므로 가져오기 라이브러리에 연결할 필요가 없습니다 컴파일러 외부 참조를 생성 하지 않습니다. 하지만 있어야는 `typedef` 또는 `using` 호출 시그니처의 호출 하는 내보낸된 함수를 정의 하는 문에 합니다.   
  
-   호출 [FreeLibrary](freelibrary-and-afxfreelibrary.md) 완료 한 후 DLL입니다.  
  
이 샘플 함수 호출 예를 들어 `LoadLibrary` "MyDLL" 이라는 DLL을 로드 하기 위해 호출 `GetProcAddress` "DLLFunc1" 라는 함수에 대 한 포인터를 가져올 수 함수를 호출 하 고 결과 저장 한 다음 호출 `FreeLibrary` DLL을 언로드할 수 있습니다. 
  
```C  
#include "windows.h"

typedef HRESULT (CALLBACK* LPFNDLLFUNC1)(DWORD,UINT*);  

HRESULT LoadAndCallSomeFunction(DWORD dwParam1, UINT * puParam2)  
{
    HINSTANCE hDLL;               // Handle to DLL  
    LPFNDLLFUNC1 lpfnDllFunc1;    // Function pointer  
    HRESULT hrReturnVal;  
      
    hDLL = LoadLibrary("MyDLL");  
    if (NULL != hDLL)  
    {  
        lpfnDllFunc1 = (LPFNDLLFUNC1)GetProcAddress(hDLL, "DLLFunc1");  
        if (NULL != lpfnDllFunc1)  
        {  
            // call the function  
            hrReturnVal = lpfnDllFunc1(dwParam1, puParam2);  
        }  
        else  
        {  
            // report the error  
            hrReturnVal = ERROR_DELAY_LOAD_FAILED;  
        }
        FreeLibrary(hDLL);
    }
    else
    {
        hrReturnVal = ERROR_DELAY_LOAD_FAILED;
    }  
    return hrReturnVal;
}
```  
  
와 달리이 예제에서는 대부분의 경우에서 호출 해야 `LoadLibrary` 및 `FreeLibrary` DLL의 여러 함수를 호출 하거나 DLL을 호출 하려고 하는 경우에 특히, 지정 된 DLL에 대 한 응용 프로그램에서 한 번만 반복 해 서 작동 합니다.  
  
## <a name="what-do-you-want-to-know-more-about"></a>추가 정보  
  
-   [가져오기 라이브러리 및 내보내기 파일을 사용한 작업](../build/reference/working-with-import-libraries-and-export-files.md)  
  
-   [Windows에서 DLL을 찾기 위해 사용 하는 검색 경로](../build/search-path-used-by-windows-to-locate-a-dll.md)  
  
## <a name="see-also"></a>참고 항목  
 [Visual C++의 DLL](../build/dlls-in-visual-cpp.md)