---
title: "연습: 동적 연결 라이브러리 만들기 및 사용(C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLL[C++], 연습"
  - "라이브러리[C++], DLL"
ms.assetid: 3ae94848-44e7-4955-bbad-7d40f493e941
caps.latest.revision: 36
caps.handback.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 연습: 동적 연결 라이브러리 만들기 및 사용(C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 단계별 연습에서는 C\+\+ 앱에 사용할 수 있도록 DLL\(동적 연결 라이브러리\)을 만드는 방법을 보여 줍니다.  라이브러리를 사용하면 코드를 매우 편리하게 다시 사용할 수 있습니다.  만드는 모든 프로그램에서 동일한 루틴을 다시 구현하는 대신 이러한 루틴을 한 번만 작성한 다음 해당 기능이 필요한 앱에서 이 루틴을 참조하게 합니다.  DLL에 코드를 삽입하여 이 코드를 참조하는 모든 앱에서 공간을 절약하고 모든 앱을 다시 컴파일할 필요 없이 DLL을 업데이트할 수 있습니다.  DLL에 대한 자세한 내용은 [Visual C\+\+의 DLL](../build/dlls-in-visual-cpp.md)을 참조하세요.  
  
 이 연습에서는 다음 작업 방법을 배웁니다.  
  
-   DLL 프로젝트를 만듭니다.  
  
-   DLL에 클래스를 추가합니다.  
  
-   로드 시간 동적 연결을 사용하여 DLL을 참조하는 콘솔 앱을 만듭니다.  
  
-   앱의 클래스에서 기능을 사용합니다.  
  
-   앱을 실행합니다.  
  
 이 연습에서는 C\+\+ 호출 규칙을 사용하는 앱에서만 호출할 수 있는 DLL을 만듭니다.  다른 언어와 함께 사용하도록 DLL을 만드는 방법에 대한 자세한 내용은 [Visual Basic 응용 프로그램에서 DLL 함수 호출](../build/calling-dll-functions-from-visual-basic-applications.md)을 참조하세요.  
  
## 사전 요구 사항  
 이 항목에서는 사용자가 C\+\+ 언어의 기본적인 사항을 알고 있는 것으로 가정합니다.  
  
### DLL\(동적 연결 라이브러리\) 프로젝트를 만들려면  
  
1.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 차례로 선택합니다.  
  
2.  **새 프로젝트** 대화 상자 왼쪽 창의 **설치됨**, **템플릿**, **Visual C\+\+**를 차례로 확장하고 **Win32**를 선택합니다.  
  
3.  가운데 창에서 **Win32 콘솔 응용 프로그램**을 선택합니다.  
  
4.  **이름** 상자에서 프로젝트 이름\(예: MathFuncsDll\)을 지정합니다.  **솔루션 이름** 상자에서 솔루션 이름\(예: DynamicLibrary\)을 지정합니다.  **확인** 단추를 선택합니다.  
  
5.  **Win32 응용 프로그램 마법사** 대화 상자의 **개요** 페이지에서 **다음** 단추를 선택합니다.  
  
6.  **응용 프로그램 설정** 페이지의 **응용 프로그램 종류** 아래에서 **DLL**을 선택합니다.  
  
7.  **마침** 단추를 선택하여 프로젝트를 만듭니다.  
  
### 동적 연결 라이브러리에 클래스를 추가하려면  
  
1.  새 클래스의 헤더 파일을 만들려면 메뉴 모음에서 **프로젝트**, **새 항목 추가**를 선택합니다.  **새 항목 추가** 대화 상자의 왼쪽 창에 있는 **Visual C\+\+**에서 **코드**를 선택합니다.  가운데 창에서 **헤더 파일 \(.h\)**을 선택합니다.  헤더 파일의 이름\(예: MathFuncsLib.h\)을 지정한 다음 **추가** 단추를 선택합니다.  빈 헤더 파일이 표시됩니다.  
  
2.  헤더 파일의 시작 부분에 다음 코드를 추가합니다.  
  
     [!code-cpp[NVC_Create_DLL_Walkthrough#100](../build/codesnippet/CPP/walkthrough-creating-and-using-a-dynamic-link-library-cpp_1.h)]  
  
3.  덧셈, 뺄셈, 곱셈, 나눗셈 같은 일반적인 산술 연산을 수행하는 MyMathFuncs라는 기본 클래스를 추가합니다.  코드는 다음과 비슷합니다.  
  
     [!code-cpp[NVC_Create_DLL_Walkthrough#101](../build/codesnippet/CPP/walkthrough-creating-and-using-a-dynamic-link-library-cpp_2.h)]  
  
     MATHFUNCSDLL\_EXPORTS 기호를 정의하면 MATHFUNCSDLL\_API 기호가 이 코드의 멤버 함수 선언에 `__declspec(dllexport)` 한정자를 설정합니다.  이 한정자를 통해 DLL로 함수를 내보낼 수 있습니다. 그러면 다른 응용 프로그램에서도 이 함수를 사용할 수 있습니다.  MATHFUNCSDLL\_EXPORTS를 정의하지 않은 경우\(예: 응용 프로그램에 헤더 파일이 없는 경우\) MATHFUNCSDLL\_API는 멤버 함수 선언에 `__declspec(dllimport)` 한정자를 정의합니다.  이 한정자는 응용 프로그램에서 함수의 가져오기를 최적화합니다.  기본적으로 DLL의 새 프로젝트 템플릿은 DLL 프로젝트에 대해 정의된 기호에 `PROJECTNAME`\_EXPORTS를 추가합니다.  다음 예제에서 MATHFUNCSDLL\_EXPORTS는 MathFuncsDll 프로젝트 빌드 시 정의됩니다.  자세한 내용은 [dllexport, dllimport](../cpp/dllexport-dllimport.md)을 참조하십시오.  
  
    > [!NOTE]
    >  명령줄에서 DLL 프로젝트를 빌드 중인 경우에는 **\/D** 컴파일러 옵션을 사용하여 MATHFUNCSDLL\_EXPORTS 기호를 정의합니다.  
  
4.  **솔루션 탐색기**의 **소스 파일** 폴더에 있는 **MathFuncsDll** 프로젝트에서 MathFuncsDll.cpp를 엽니다.  
  
5.  소스 파일에서 MyMathFuncs의 기능을 구현합니다.  코드는 다음과 비슷합니다.  
  
     [!code-cpp[NVC_Create_DLL_Walkthrough#110](../build/codesnippet/CPP/walkthrough-creating-and-using-a-dynamic-link-library-cpp_3.cpp)]  
  
6.  메뉴 모음에서 **빌드**, **솔루션 빌드**를 선택하여 동적 연결 라이브러리를 컴파일합니다.  
  
    > [!NOTE]
    >  **빌드** 메뉴가 표시되지 않는 Express Edition을 사용하는 경우 메뉴 모음에서 **도구**, **설정**, **전문가 설정**을 선택하여 사용하도록 설정합니다. 그런 다음 **빌드**, **솔루션 빌드**를 선택합니다.  
  
    > [!NOTE]
    >  명령줄에서 프로젝트를 빌드하는 경우 **\/LD** 컴파일러 옵션을 사용하여 출력 파일이 DLL이 되도록 지정합니다.  자세한 내용은 [\/MD, \/MT, \/LD\(런타임 라이브러리 사용\)](../build/reference/md-mt-ld-use-run-time-library.md)을 참조하십시오.  **\/EHsc** 컴파일러 옵션을 사용하여 C\+\+ 예외 처리를 가능하도록 합니다.  자세한 내용은 [\/EH\(예외 처리 모델\)](../build/reference/eh-exception-handling-model.md)을 참조하십시오.  
  
### DLL을 참조하는 앱을 만들려면  
  
1.  방금 만든 DLL을 참조하여 사용하는 C\+\+ 앱을 만들려면 메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 선택합니다.  
  
2.  왼쪽 창의 **Visual C\+\+**에서 **Win32**를 선택합니다.  
  
3.  가운데 창에서 **Win32 콘솔 응용 프로그램**을 선택합니다.  
  
4.  **이름** 상자에서 프로젝트 이름\(예: MyExecRefsDll\)을 지정합니다.  **솔루션** 옆에 있는 드롭다운 목록에서 **솔루션에 추가**를 선택합니다.  이렇게 하면 새 프로젝트가 DLL이 포함된 동일한 솔루션에 추가됩니다.  **확인** 단추를 선택합니다.  
  
5.  **Win32 응용 프로그램 마법사** 대화 상자의 **개요** 페이지에서 **다음** 단추를 선택합니다.  
  
6.  **응용 프로그램 설정** 페이지의 **응용 프로그램 종류** 아래에서 **콘솔 응용 프로그램**을 선택합니다.  
  
7.  **응용 프로그램 설정** 페이지의 **추가 옵션**에서 **미리 컴파일된 헤더** 확인란을 선택 취소합니다.  
  
8.  **마침** 단추를 선택하여 프로젝트를 만듭니다.  
  
### 앱에서 클래스 라이브러리의 기능을 사용하려면  
  
1.  콘솔 응용 프로그램을 만들면 빈 프로그램이 만들어집니다.  소스 파일의 이름은 앞에서 선택한 이름과 동일하게 설정됩니다.  이 예제에서 소스 파일의 이름은 MyExecRefsDll.cpp입니다.  
  
2.  DLL에서 방금 만든 수학 루틴을 앱에서 사용하려면 해당 루틴을 참조해야 합니다.  루틴을 참조하려면 **솔루션 탐색기**에서 MyExecRefsDll 프로젝트를 선택한 다음 메뉴 모음에서 **프로젝트**, **참조**를 선택합니다.  **속성 페이지** 대화 상자에서 **공용 속성** 노드를 확장하고 **프레임워크 및 참조**를 선택한 다음 **새 참조 추가** 단추를 선택합니다.  **참조** 대화 상자에 대한 자세한 내용은 [참조 추가](../ide/adding-references-in-visual-cpp-projects.md)를 참조하십시오.  
  
3.  **참조 추가** 대화 상자에는 참조할 수 있는 라이브러리의 목록이 표시됩니다.  **프로젝트** 탭에는 현재 솔루션의 모든 프로젝트와 이 프로젝트에 포함된 라이브러리가 나열됩니다.  **프로젝트** 탭에서 MathFuncsDll 옆에 있는 확인란을 선택한 다음 **확인** 단추를 선택합니다.  
  
4.  DLL의 헤더 파일을 참조하려면 포함된 디렉터리 경로를 수정해야 합니다.  수정하려면 **속성 페이지** 대화 상자에서 **구성 속성** 노드, **C\/C\+\+** 노드를 차례로 확장한 다음 **일반**을 선택합니다.  **추가 포함 디렉터리** 옆에서 MathFuncsDll.h 헤더 파일의 위치 경로를 지정합니다.  상대 경로\(예: ..\\MathFuncsDll\\\)를 사용한 다음 **확인** 단추를 선택할 수 있습니다.  
  
5.  이제 이 응용 프로그램에서 MyMathFuncs 클래스를 사용할 수 있습니다.  다음 코드로 MyExecRefsDll.cpp의 내용을 바꿉니다.  
  
     [!code-cpp[NVC_Create_DLL_Walkthrough#120](../build/codesnippet/CPP/walkthrough-creating-and-using-a-dynamic-link-library-cpp_4.cpp)]  
  
6.  메뉴 모음에서 **빌드**, **솔루션 빌드**를 선택하여 실행 파일을 빌드합니다.  
  
### 응용 프로그램을 실행하려면  
  
1.  MyExecRefsDll이 기본 프로젝트로 선택되어 있는지 확인합니다.  **솔루션 탐색기**에서 MyExecRefsDll을 선택한 다음 메뉴 모음에서 **프로젝트**, **시작 프로젝트로 설정**을 선택합니다.  
  
2.  프로젝트를 실행하려면 메뉴 모음에서 **디버그**, **디버깅하지 않고 시작**을 선택합니다.  다음과 같은 결과가 출력됩니다.  
  
  **a \+ b \= 106.4**  
**a \- b \= \-91.6**  
**a \* b \= 732.6**  
**a \/ b \= 0.0747475**  
**Caught exception: b cannot be zero\!**  
  
## 참고 항목  
 [Visual C\+\+ Guided Tour](http://msdn.microsoft.com/ko-kr/499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [Visual C\+\+의 DLL](../build/dlls-in-visual-cpp.md)   
 [데스크톱 응용 프로그램 배포](../ide/deploying-native-desktop-applications-visual-cpp.md)   
 [연습: 프로그램 배포\(C\+\+\)](../ide/walkthrough-deploying-your-program-cpp.md)   
 [Visual Basic 응용 프로그램에서 DLL 함수 호출](../build/calling-dll-functions-from-visual-basic-applications.md)