---
title: '연습: 컴파일 C + + /CLI 프로그램 명령줄에 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
ms.assetid: cef41c88-faf9-439d-8423-25aa3f5674dd
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d509bc9890f4fa5ccebbd6ae3d1e3bcb3dbb0d93
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-compiling-a-ccli-program-on-the-command-line"></a>연습: 명령줄에서 C++/CLI 프로그램 컴파일
CLR(공용 언어 런타임)을 대상으로 하는 Visual C++ 프로그램을 만들어 .NET Framework를 사용하여 명령줄에서 빌드할 수 있습니다. Visual C++은 .NET 프로그래밍 모델을 대상으로 하는 추가 형식 및 연산자가 있는 C++/CLI 프로그래밍 언어를 지원합니다. 에 대 한 C + + /CLI 언어 참조 [순수 c + +: Hello, C + + CLI](http://msdn.microsoft.com/magazine/cc163681.aspx)합니다. 일반 정보를 참조 하십시오. [.NET 프로그래밍 C + + /cli CLI (Visual c + +)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)합니다.  
  
 이 연습에서는 텍스트 편집기를 사용하여 기본적인 C++/CLI 프로그램을 만든 다음 명령줄에서 컴파일합니다. 여기에 나와 있는 내용을 입력하는 대신 C++/CLI 프로그램을 직접 사용할 수도 있고 다른 도움말 문서의 C++/CLI 코드 샘플을 사용할 수도 있습니다. 이 기술은 UI 요소가 없는 소형 모듈을 빌드하고 테스트하는 데 유용합니다.  
  
> [!NOTE]
>  또한 Visual Studio IDE를 사용하여 C++/CLI 프로그램을 컴파일할 수 있습니다. 자세한 내용은 참조 [연습: Visual Studio에서 CLR를 대상으로 하는 c + + 프로그램 컴파일](../ide/walkthrough-compiling-a-cpp-program-that-targets-the-clr-in-visual-studio.md)합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 개발자는 C++ 언어의 기본적인 사항을 알고 있어야 합니다.  
  
## <a name="compiling-a-ccli-program"></a>C++/CLI 프로그램 컴파일  
 다음 단계는 .NET Framework 클래스를 사용하는 C++/CLI 콘솔 응용 프로그램을 컴파일하는 방법을 보여줍니다.  
  
 C +에 대 한 컴파일을 사용 하도록 설정 하려면 + /cli를 사용 해야 합니다는 [/clr](../build/reference/clr-common-language-runtime-compilation.md) 컴파일러 옵션입니다. Visual C++ 컴파일러는 MSIL 코드를 포함하거나 MSIL 코드와 네이티브 코드가 혼합되어 있는 .exe 파일을 생성하여 필수 .NET Framework 라이브러리에 연결합니다.  
  
#### <a name="to-compile-a-ccli-application-on-the-command-line"></a>명령줄에서 C++/CLI 응용 프로그램을 컴파일하려면  
  
1.  열기는 **개발자 명령 프롬프트** 창. 구체적인 지침은 참조 [개발자 명령 프롬프트 창을 열려면](../build/building-on-the-command-line.md#developer_command_prompt)합니다.  
  
     컴퓨터 운영 체제 및 구성에 따라 코드를 정상적으로 컴파일하려면 관리자 자격 증명이 필요할 수 있습니다. 명령 프롬프트 창을 관리자 권한으로을 실행 하려면 마우스 오른쪽 단추를 명령 프롬프트에 대 한 바로 가기 메뉴를 연 다음 선택 **자세한**, **관리자 권한으로 실행**합니다.  
  
2.  명령 프롬프트에서 다음을 입력 **메모장 basicclr.cpp**합니다.  
  
     선택 **예** 때 메시지가 표시 되는 파일을 만듭니다.  
  
3.  메모장에 다음 줄을 입력합니다.  
  
    ```  
    int main()  
    {  
        System::Console::WriteLine("This is a C++/CLI program.");  
    }  
    ```  
  
4.  메뉴 모음에서 **파일**, **저장**합니다.  
  
     <xref:System.Console> 네임스페이스에서 .NET Framework 클래스(<xref:System>)를 사용하는 Visual C++ 소스 파일을 만들었습니다.  
  
5.  명령 프롬프트에서 다음을 입력 **cl /clr basicclr.cpp**합니다. cl.exe 컴파일러는 이 소스 파일을 MSIL이 포함된 .obj 파일로 컴파일한 다음 링커를 실행하여 실행 프로그램인 basicclr.exe를 생성합니다.  
  
6.  Basicclr.exe 프로그램을 명령 프롬프트에서를 실행 하려면 입력 **basicclr**합니다.  
  
     프로그램이 다음 텍스트를 표시하고 종료됩니다.  
  
    ```Output  
    This is a C++/CLI program.  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [C + + 언어 참조](../cpp/cpp-language-reference.md)   
 [C/C++ 프로그램 빌드](../build/building-c-cpp-programs.md)   
 [컴파일러 옵션](../build/reference/compiler-options.md)