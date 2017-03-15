---
title: "연습: 명령줄에서 C++/CLI 프로그램 컴파일 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: cef41c88-faf9-439d-8423-25aa3f5674dd
caps.latest.revision: 11
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 연습: 명령줄에서 C++/CLI 프로그램 컴파일
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

CLR\(공용 언어 런타임\)을 대상으로 하는 Visual C\+\+ 프로그램을 만들어 .NET Framework를 사용하여 명령줄에서 빌드할 수 있습니다.  Visual C\+\+은 .NET 프로그래밍 모델을 대상으로 하는 추가 형식 및 연산자가 있는 C\+\+\/CLI 프로그래밍 언어를 지원합니다.  C\+\+\/CLI 언어에 대한 지침은 [Pure C\+\+: Hello, C\+\+\/CLI](http://msdn.microsoft.com/magazine/cc163681.aspx)를 참조하세요.  일반 정보는 [C\+\+\/CLI를 사용한 .NET 프로그래밍](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)을 참조하세요.  
  
 이 연습에서는 텍스트 편집기를 사용하여 기본적인 C\+\+\/CLI 프로그램을 만든 다음 명령줄에서 컴파일합니다.  여기에 나와 있는 내용을 입력하는 대신 C\+\+\/CLI 프로그램을 직접 사용할 수도 있고 다른 도움말 문서의 C\+\+\/CLI 코드 샘플을 사용할 수도 있습니다.  이 기술은 UI 요소가 없는 소형 모듈을 빌드하고 테스트하는 데 유용합니다.  
  
> [!NOTE]
>  또한 Visual Studio IDE를 사용하여 C\+\+\/CLI 프로그램을 컴파일할 수 있습니다.  자세한 내용은 [연습: Visual Studio에서 CLR을 대상으로 하는 C\+\+ 프로그램 컴파일](../ide/walkthrough-compiling-a-cpp-program-that-targets-the-clr-in-visual-studio.md)을 참조하십시오.  
  
## 사전 요구 사항  
 개발자는 C\+\+ 언어의 기본적인 사항을 알고 있어야 합니다.  
  
## C\+\+\/CLI 프로그램 컴파일  
 다음 단계는 .NET Framework 클래스를 사용하는 C\+\+\/CLI 콘솔 응용 프로그램을 컴파일하는 방법을 보여줍니다.  
  
 C\+\+\/CLI에 대해 컴파일을 사용하도록 설정하려면 [\/clr](../build/reference/clr-common-language-runtime-compilation.md) 컴파일러 옵션을 사용해야 합니다.  Visual C\+\+ 컴파일러는 MSIL 코드를 포함하거나 MSIL 코드와 네이티브 코드가 혼합되어 있는 .exe 파일을 생성하여 필수 .NET Framework 라이브러리에 연결합니다.  
  
#### 명령줄에서 C\+\+\/CLI 응용 프로그램을 컴파일하려면  
  
1.  **개발자 명령 프롬프트** 창을 엽니다.  **시작** 창에서 **앱**을 엽니다.  사용 중인 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] 버전에서 **Visual Studio Tools** 폴더를 연 다음 **개발자 명령 프롬프트** 바로 가기를 선택합니다. 명령 프롬프트 창을 여는 방법에 대한 자세한 내용은 [명령줄 빌드를 위한 경로 및 환경 변수 설정](../build/setting-the-path-and-environment-variables-for-command-line-builds.md)을 참조하세요.  
  
     컴퓨터 운영 체제 및 구성에 따라 코드를 정상적으로 컴파일하려면 관리자 자격 증명이 필요할 수 있습니다.  관리자로 명령 프롬프트 창을 실행하려면 **개발자 명령 프롬프트**의 바로 가기 메뉴를 연 다음 **관리자 권한으로 실행**을 선택합니다.  
  
2.  명령 프롬프트에 **notepad basicclr.cpp**를 입력합니다.  
  
     파일을 만들 것인지 묻는 메시지가 나타나면 **예**를 선택합니다.  
  
3.  메모장에 다음 줄을 입력합니다.  
  
    ```  
    int main()  
    {  
        System::Console::WriteLine("This is a C++/CLI program.");  
    }  
    ```  
  
4.  메뉴 모음에서 **파일**, **저장**을 선택합니다.  
  
     <xref:System> 네임스페이스에서 .NET Framework 클래스\(<xref:System.Console>\)를 사용하는 Visual C\+\+ 소스 파일을 만들었습니다.  
  
5.  명령 프롬프트에 **cl \/clr basicclr.cpp**를 입력합니다.  cl.exe 컴파일러는 이 소스 파일을 MSIL이 포함된 .obj 파일로 컴파일한 다음 링커를 실행하여 실행 프로그램인 basicclr.exe를 생성합니다.  
  
6.  basicclr.exe 프로그램을 실행하려면 명령 프롬프트에 **basicclr**을 입력합니다.  
  
     프로그램이 다음 텍스트를 표시하고 종료됩니다.  
  
  **This is a C\+\+\/CLI program.**  
  
## 참고 항목  
 [Visual C\+\+ Guided Tour](http://msdn.microsoft.com/ko-kr/499cb66f-7df1-45d6-8b6b-33d94fd1f17c)   
 [C\+\+ 언어 참조](../cpp/cpp-language-reference.md)   
 [C\/C\+\+ 프로그램 빌드](../build/building-c-cpp-programs.md)   
 [컴파일러 옵션](../build/reference/compiler-options.md)