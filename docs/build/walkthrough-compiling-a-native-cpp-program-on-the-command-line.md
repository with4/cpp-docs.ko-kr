---
title: "연습: 명령줄에서 네이티브 C++ 프로그램 컴파일 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "명령줄 응용 프로그램[C++], native"
  - "프로그램 컴파일[C++]"
  - "네이티브 코드[C++]"
  - "Visual C++, 네이티브 코드"
ms.assetid: b200cfd1-0440-498f-90ee-7ecf92492dc0
caps.latest.revision: 63
caps.handback.revision: 57
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 연습: 명령줄에서 네이티브 C++ 프로그램 컴파일
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+에는 기본적인 콘솔 앱부터 유니버설 Windows 앱, Windows 스토어 앱 및 .NET 구성 요소에 이르기까지 다양한 프로그램을 만드는 데 사용할 수 있는 명령줄 C\+\+ 컴파일러가 포함되어 있습니다.  
  
 이 연습에서는 텍스트 편집기를 사용하여 기본적인 Visual C\+\+ 콘솔 프로그램을 만들고 명령줄에서 컴파일하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  또한 Visual Studio IDE\(통합 개발 환경\)를 사용하여 Visual C\+\+ 프로그램을 컴파일할 수 있습니다. 자세한 내용은 [연습: 프로젝트 및 솔루션 작업\(C\+\+\)](../ide/walkthrough-working-with-projects-and-solutions-cpp.md)을 참조하세요.  
  
 이 연습에서는 표시되는 내용을 입력하는 대신 Visual C\+\+ 프로그램을 사용하거나 다른 도움말 문서의 Visual C\+\+ 코드 샘플을 사용할 수 있습니다.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 Visual C\+\+ 구성 요소가 포함된 Visual Studio 버전이 있어야 합니다. C\+\+ 언어의 기본적인 사항을 이해하면 도움이 됩니다. 이러한 지침에서는 Windows 10 및 Visual Studio 2015를 사용 중이라고 가정하지만 다른 환경 및 버전에 대한 지침도 이와 유사합니다.  
  
### Visual C\+\+ 소스 파일을 만들고 명령줄에서 컴파일하려면  
  
1.  먼저 **개발자 명령 프롬프트**를 엽니다. Visual C\+\+ 컴파일러를 실행하려면 특수한 명령 환경이 필요하므로 이 연습에 대해 일반적인 명령 프롬프트를 사용할 수 없습니다.  
  
     Windows **시작** 메뉴에서 **모든 앱**을 엽니다. 아래로 스크롤하여 사용 중인 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] 버전에 대한 **Visual Studio** 폴더를 찾아서 연 다음 **개발자 명령 프롬프트** 바로 가기를 선택합니다.  
  
2.  프로그램을 저장할 새 디렉터리를 만듭니다.**개발자 명령 프롬프트** 창에서 `cd \` 명령을 입력하여 디렉터리를 드라이브 루트로 변경합니다.`md examples` 명령을 입력하여 예제 코드에 대한 디렉터리를 만듭니다. 그런 다음 `cd examples` 명령을 입력하여 현재 작업 디렉터리로 만듭니다. 첫 번째 프로그램은 여기로 이동합니다.  
  
3.  명령 프롬프트에서 **notepad hello.cpp**를 입력합니다.  
  
     파일을 만들 것인지 묻는 메시지가 나타나면 **예**를 선택합니다. 코드를 입력할 수 있도록 준비된 빈 메모장 창이 열립니다.  
  
4.  메모장에 다음 줄을 입력합니다.  
  
    ```cpp  
    #include <iostream> using namespace std; void main() { cout << "Hello, world, from Visual C++!" << endl; }  
    ```  
  
     이는 화면에 한 줄의 텍스트를 쓴 다음 종료되는 매우 간단한 프로그램입니다. 오류를 최소화하기 위해 이 코드를 복사하여 메모장에 붙여넣습니다.  
  
5.  작업을 저장합니다. 메모장의 **파일** 메뉴에서 **저장**을 선택합니다.  
  
     Visual C\+\+ 소스 파일을 만들었습니다.  
  
6.  명령 프롬프트에서 `cl /EHsc hello.cpp`를 입력하여 프로그램을 컴파일합니다.  
  
     cl.exe 컴파일러는 컴파일된 코드가 포함된 .obj 파일을 만든 다음 링커를 실행하여 실행 프로그램인 hello.exe를 만듭니다. 이 이름은 컴파일러에서 표시하는 출력 정보 줄에 나타납니다. 컴파일러 출력은 다음과 비슷합니다.  
  
    ```Output  
    Microsoft (R) C/C++ Optimizing Compiler Version 19.00.23504 for x86 Copyright (C) Microsoft Corporation.  All rights reserved. hello.cpp Microsoft (R) Incremental Linker Version 14.00.23504.0 Copyright (C) Microsoft Corporation.  All rights reserved. /out:hello.exe hello.obj  
    ```  
  
     오류가 있는 경우 메모장에서 코드를 검사하여 예제와 일치하는지 확인합니다. 변경 내용을 저장한 후 컴파일러 명령을 다시 실행합니다.  cl 명령이 없는 경우 일반 명령 창이 아닌 개발자 명령 프롬프트를 사용 중인지 확인합니다. 아직 설치되지 않은 경우 Visual Studio 설치 프로그램에서 Visual C\+\+ 구성 요소를 설치해야 할 수도 있습니다.  
  
7.  hello.exe 프로그램을 실행하려면 명령 프롬프트에서 `hello`를 입력합니다.  
  
     프로그램이 다음 텍스트를 표시하고 종료됩니다.  
  
    ```Output  
    Hello, world, from Visual C++!  
    ```  
  
     축하합니다. 명령줄 도구를 사용하여 프로그램을 만들고 컴파일했습니다.  
  
## 다음 단계  
 명령줄 도구를 사용하기 위해 개발자 명령 프롬프트 창을 여는 방법에 대한 자세한 내용은 [명령줄 빌드를 위한 경로 및 환경 변수 설정](../build/setting-the-path-and-environment-variables-for-command-line-builds.md)을 참조하세요.  
  
 이 연습에서 코드를 성공적으로 컴파일하려면 컴퓨터 운영 체제 및 구성에 따라 관리자 자격 증명이 필요할 수 있습니다. 관리자 권한으로 개발자 명령 프롬프트 창을 실행하려면 마우스 오른쪽 단추를 클릭하여 **개발자 명령 프롬프트**의 바로 가기 메뉴를 연 다음 **관리자 권한으로 실행**을 선택합니다.  
  
 **\/EHsc** 명령줄 옵션은 컴파일러에 C\+\+ 예외 처리를 사용하도록 지시합니다. 자세한 내용은 [\/EH\(예외 처리 모델\)](../build/reference/eh-exception-handling-model.md)을 참조하세요.  
  
## 참고 항목  
 [Visual C\+\+ 둘러보기](http://msdn.microsoft.com/ko-kr/499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [C\+\+ 언어 참조](../cpp/cpp-language-reference.md)   
 [C\/C\+\+ 프로그램 빌드](../build/building-c-cpp-programs.md)   
 [컴파일러 옵션](../build/reference/compiler-options.md)