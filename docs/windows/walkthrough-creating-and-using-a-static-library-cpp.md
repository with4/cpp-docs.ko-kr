---
title: '연습: 만들기 및 정적 라이브러리 (c + +)를 사용 하 여 | Microsoft Docs'
ms.custom: get-started-article
ms.date: 07/12/2018
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- libraries [C++], static
- static libraries [C++]
ms.assetid: 3cc36411-7d66-4240-851e-dacb9a8fd6ac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1bcbf5747b667615c96ced3488e16f2a8fc0ef2d
ms.sourcegitcommit: 9ad287c88bdccee2747832659fe50c2e5d682a0b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/13/2018
ms.locfileid: "39034805"
---
# <a name="walkthrough-creating-and-using-a-static-library-c"></a>연습: 정적 라이브러리 만들기 및 사용(C++)
이 단계별 연습에서는 C++ 앱에 사용할 수 있도록 정적 라이브러리(.lib 파일)를 만드는 방법을 보여 줍니다. 정적 라이브러리를 사용하면 코드를 매우 편리하게 다시 사용할 수 있습니다. 기능이 필요한 모든 응용 프로그램에서 동일한 루틴을 다시 구현하는 대신 정적 라이브러리에 한 번만 작성한 다음 응용 프로그램에서 루틴을 참조하도록 합니다. 정적 라이브러리에서 연결된 코드는 응용 프로그램의 일부가 되므로 코드를 사용하기 위해 다른 파일을 설치할 필요가 없습니다.  
  
 이 연습에서는 다음 작업 방법을 배웁니다.  
  
-   [정적 라이브러리 프로젝트 만들기](#CreateLibProject)  
  
-   [정적 라이브러리에 클래스 추가](#AddClassToLib)  
  
-   [정적 라이브러리를 참조 하는 c + + 콘솔 앱 만들기](#CreateAppToRefTheLib)  
  
-   [앱에서 정적 라이브러리의 기능을 사용 하 여](#UseLibInApp)  
  
-   [앱 실행](#RunApp)  
  
## <a name="prerequisites"></a>전제 조건  
 C++ 언어의 기본적인 사항을 알고 있어야 합니다.  
  
##  <a name="CreateLibProject"></a> 정적 라이브러리 프로젝트 만들기  
  
#### <a name="to-create-a-static-library-project"></a>정적 라이브러리 프로젝트를 만들려면  
  
1.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.  
  
2. 왼쪽된 창에서 합니다 **새 프로젝트** 대화 상자에서 **설치 됨, Visual c + +** 를 선택한 후 **Windows Desktop**합니다.
  
3. 가운데 창에서 선택 **Windows 데스크톱 마법사**합니다.  
  
4.  **이름**상자에서 프로젝트 이름(예: **MathFuncsLib** )을 지정합니다. **솔루션 이름**상자에서 솔루션 이름(예: **StaticLibrary** )을 지정합니다. **확인** 단추를 선택합니다.  
  
5. 아래 **응용 프로그램 유형을**, 정적 라이브러리 (.lib)를 선택 합니다.  
  
6. 아래 **추가 옵션**의 선택을 취소 합니다 **미리 컴파일된 헤더** 확인란 합니다.
  
7. 선택할 **확인** 프로젝트를 만듭니다.  
 
##  <a name="AddClassToLib"></a> 정적 라이브러리에 클래스 추가  
  
#### <a name="to-add-a-class-to-the-static-library"></a>정적 라이브러리에 클래스를 추가하려면  
  
1.  새 클래스에 대한 헤더 파일을 만들려면 **솔루션 탐색기** 에서 **MathFuncsLib**프로젝트에 대한 바로 가기 메뉴를 연 후 **추가**, **새 항목**을 선택합니다. **새 항목 추가** 대화 상자의 왼쪽 창에 있는 **Visual C++** 에서 **코드**를 선택합니다. 가운데 창에서 **헤더 파일 (.h)** 을 선택합니다. 헤더 파일의 이름(예: **MathFuncsLib.h**)을 지정하고 **추가** 단추를 선택합니다. 빈 헤더 파일이 표시됩니다.  
  
2.  덧셈, 뺄셈, 곱셈, 나눗셈 같은 일반적인 산술 연산을 수행하는 **MyMathFuncs** 라는 클래스를 추가합니다. 코드는 다음과 비슷합니다.  
  
     [!code-cpp[NVC_Walkthrough_Create_Static_Lib#100](../windows/codesnippet/CPP/walkthrough-creating-and-using-a-static-library-cpp_1.h)]  
  
3.  새 클래스에 대한 소스 파일을 만들려면 **솔루션 탐색기** 에서 **MathFuncsLib**프로젝트에 대한 바로 가기 메뉴를 연 후 **추가**, **새 항목**을 선택합니다. **새 항목 추가** 대화 상자의 왼쪽 창에 있는 **Visual C++** 에서 **코드**를 선택합니다. 가운데 창에서 **C++ 파일 (.cpp)** 을 선택합니다. 소스 파일의 이름(예: **MathFuncsLib.cpp**)을 지정하고 **추가** 단추를 선택합니다. 빈 소스 파일이 표시됩니다.  
  
4.  이 소스 파일을 사용하여 **MyMathFuncs**의 기능을 구현합니다. 코드는 다음과 비슷합니다.  
  
     [!code-cpp[NVC_Walkthrough_Create_Static_Lib#110](../windows/codesnippet/CPP/walkthrough-creating-and-using-a-static-library-cpp_2.cpp)]  
  
5.  메뉴 모음에서 **빌드**, **솔루션 빌드** 를 선택하여 정적 라이브러리를 컴파일합니다. 이렇게 하면 다른 프로그램에서 사용할 수 있는 정적 라이브러리가 작성됩니다.  
  
    > [!NOTE]
    >  Visual Studio 명령줄에서 빌드하는 경우 프로그램을 빌드하는 데 두 단계를 거쳐야 합니다. 먼저 **cl /c /EHsc MathFuncsLib.cpp** 를 실행하여 코드를 컴파일하고 **MathFuncsLib.obj**라는 개체 파일을 만듭니다. (합니다 **cl** 명령은 Cl.exe 컴파일러를 호출 하며 **/c** 옵션 연결 없는 컴파일을 지정 합니다. 자세한 내용은 [(컴파일 없이 링크 사용)는 /c](../build/reference/c-compile-without-linking.md).) 둘째, 실행 **MathFuncsLib.obj lib** 정적 라이브러리를 만들고 코드를 링크 합니다 **MathFuncsLib.lib**합니다. **lib** 명령은 Lib.exe 라이브러리 관리자를 호출합니다. 자세한 내용은 [LIB Reference](../build/reference/lib-reference.md)를 참조하세요.  
  
##  <a name="CreateAppToRefTheLib"></a> 정적 라이브러리를 참조 하는 c + + 콘솔 앱 만들기  
  
#### <a name="to-create-a-c-console-app-that-references-the-static-library"></a>정적 라이브러리를 참조하는 C++ 콘솔 앱을 만들려면  
  
1.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.  
  
2. 왼쪽된 창에서 합니다 **새 프로젝트** 대화 상자에서 **설치 됨, Visual c + +** 를 선택한 후 **Windows Desktop**합니다.  

3. 가운데 창에서 선택 **Windows 데스크톱 마법사**합니다.  
  
4.  **이름**상자에서 프로젝트 이름(예: **MyExecRefsLib** )을 지정합니다. **솔루션**옆에 있는 드롭다운 목록에서 **솔루션에 추가**를 선택합니다. 이렇게 하면 새 프로젝트가 정적 라이브러리를 포함하는 솔루션에 추가됩니다. **확인** 단추를 선택합니다.  
5. 아래 **응용 프로그램 종류**를 선택 **콘솔 응용 프로그램 (.exe)** 합니다.

6. 아래 **Additioal 옵션**의 선택을 취소 합니다 **미리 컴파일된 헤더** 확인란 합니다.

7. 선택할 **확인** 프로젝트를 만듭니다.  
  
##  <a name="UseLibInApp"></a> 앱에서 정적 라이브러리의 기능을 사용 하 여  
  
#### <a name="to-use-the-functionality-from-the-static-library-in-the-app"></a>앱에서 정적 라이브러리의 기능을 사용하려면  
  
1.  콘솔 응용 프로그램을 만들면 빈 프로그램이 만들어집니다. 소스 파일의 이름은 앞에서 선택한 이름과 동일하게 설정됩니다. 이 예제에서 소스 파일의 이름은 **MyExecRefsLib.cpp**입니다.  
  
2.  정적 라이브러리에서 수학 루틴을 사용하기 전에 이를 참조해야 합니다. 이렇게 하려면에서 MyExecRefsLib 프로젝트에 대 한 바로 가기 메뉴를 열고 **솔루션 탐색기**를 선택한 후 **추가, 참조**합니다.  
  
3.  **참조 추가** 대화 상자에는 참조할 수 있는 라이브러리의 목록이 표시됩니다. **프로젝트** 탭에는 현재 솔루션의 모든 프로젝트와 이 프로젝트에 포함된 라이브러리가 나열됩니다. **프로젝트** 탭에서 **MathFuncsLib** 확인란을 선택한 다음 **확인** 단추를 선택합니다.  
  
4.  **MathFuncsLib.h** 헤더 파일을 참조하려면 포함된 디렉터리 경로를 수정해야 합니다. **MyExecRefsLib** 에 대한 **속성 페이지**대화 상자에서 **구성 속성** 노드, **C/C++** 노드를 차례로 확장한 다음 **일반**을 선택합니다. **추가 포함 디렉터리**옆에서 **MathFuncsLib** 디렉터리의 경로를 지정하거나 해당 경로를 찾습니다.  
  
     디렉터리 경로를 찾으려면 속성 값 드롭다운 목록 상자를 열고 **편집**을 선택합니다. 에 **Additional Include Directories** 대화 상자의 텍스트 상자에서 빈 줄을 선택 하 고 선택한 다음 줄임표 단추 (**...** ) 줄의 끝입니다. **디렉터리 선택** 대화 상자에서 **MathFuncsLib** 디렉터리를 선택하고 **폴더 선택** 단추를 선택하여 선택 내용을 저장한 후 대화 상자를 닫습니다. **추가 포함 디렉터리** 대화 상자에서 **확인** 단추를 선택한 후 **속성 페이지** 대화 상자에서 **확인** 단추를 선택하여 프로젝트에 변경 내용을 저장합니다.  
  
5.  이제 이 응용 프로그램에서 **MyMathFuncs** 클래스를 사용할 수 있습니다. 이렇게 하려면 **MyExecRefsLib.cpp** 의 내용을 다음 코드로 바꿉니다.  
  
     [!code-cpp[NVC_Walkthrough_Create_Static_Lib#120](../windows/codesnippet/CPP/walkthrough-creating-and-using-a-static-library-cpp_3.cpp)]  
  
6.  메뉴 모음에서 **빌드**, **솔루션 빌드** 를 선택하여 실행 파일을 빌드합니다.  
  
##  <a name="RunApp"></a> 앱 실행  
  
#### <a name="to-run-the-app"></a>앱을 실행하려면  
  
1.  **솔루션 탐색기** 에서 **MyExecRefsLib** 의 바로 가기 메뉴를 열고 **시작 프로젝트로 설정**을 선택하여 **MyExecRefsLib**가 기본 프로젝트로 선택되었는지 확인합니다.  
  
2.  프로젝트를 실행하려면 메뉴 모음에서 **디버그**, **디버깅하지 않고 시작**을 선택합니다. 다음과 같은 결과가 출력됩니다.  
  
    ```Output  
    a + b = 106.4  
    a - b = -91.6  
    a * b = 732.6  
    a / b = 0.0747475  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [연습: 동적 연결 라이브러리 만들기 및 사용(C++)](../build/walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)   
 [데스크톱 응용 프로그램(Visual C++)](../windows/desktop-applications-visual-cpp.md)
