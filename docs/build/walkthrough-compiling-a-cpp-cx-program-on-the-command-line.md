---
title: "연습: 컴파일 C + + /CX 프로그램 명령줄에 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 626f5544-69ed-4736-83a9-f11389b371b2
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 677779aa8550869fe0859974b2aa4bbbb1c23d83
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-compiling-a-ccx-program-on-the-command-line"></a>연습: 명령줄에서 C++/CX 프로그램 컴파일
Windows 런타임을 대상으로 하는 Visual C++ 프로그램을 만들어 명령줄에서 빌드할 수 있습니다. Visual C++는 Windows 런타임 프로그래밍 모델을 대상으로 하는 추가 형식 및 연산자가 있는 Visual C++ 구성 요소 확장(C++/CX)을 지원합니다. C++/CX를 사용하여 Windows Phone 8.1, Windows 스토어 및 Windows 데스크톱용 앱을 빌드할 수 있습니다. 자세한 내용은 참조 [A C+ 둘러보기 + CX](http://msdn.microsoft.com/magazine/dn166929.aspx) 및 [런타임 플랫폼용 구성 요소 확장명](../windows/component-extensions-for-runtime-platforms.md)합니다.  
  
 이 연습에서는 텍스트 편집기를 사용하여 기본적인 C++/CX 프로그램을 만든 다음 명령줄에서 컴파일합니다. 여기에 나와 있는 내용을 입력하는 대신 C++/CX 프로그램을 직접 사용할 수도 있고 다른 도움말 문서의 C++/CX 코드 샘플을 사용할 수도 있습니다. 이 기술은 UI 요소가 없는 소형 모듈을 빌드하고 테스트하는 데 유용합니다.  
  
> [!NOTE]
>  또한 Visual Studio IDE를 사용하여 C++/CX 프로그램을 컴파일할 수 있습니다. IDE는 명령줄에서는 제공되지 않는 디자인, 디버그, 에뮬레이션 및 배포 지원을 포함하므로 IDE를 사용하여 Windows 스토어 앱을 빌드하는 것이 좋습니다. 자세한 내용은 참조 [기본 c + + 스토어 앱 만들기](http://msdn.microsoft.com/library/windows/apps/dn263168)합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 개발자는 C++ 언어의 기본적인 사항을 알고 있어야 합니다.  
  
## <a name="compiling-a-ccx-program"></a>C++/CX 프로그램 컴파일  
 C +에 대 한 컴파일을 사용 하도록 설정 하려면 + /cli를 사용 해야 /CX에서는 [/ZW](../build/reference/zw-windows-runtime-compilation.md) 컴파일러 옵션입니다. Visual C++ 컴파일러는 Windows 런타임을 대상으로 하는 .exe 파일을 생성하고 필수 라이브러리에 연결합니다.  
  
#### <a name="to-compile-a-ccx-application-on-the-command-line"></a>명령줄에서 C++/CX 응용 프로그램을 컴파일하려면  
  
1.  열기는 **개발자 명령 프롬프트** 창. (에 **시작** 창을 열어 **앱**합니다. 열기는 **Visual Studio Tools** 버전 아래에 폴더 [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]를 선택한 후는 **개발자 명령 프롬프트** 바로 가기.) 개발자 명령 프롬프트 창을 여는 방법에 대 한 자세한 내용은 참조 [명령줄에서 빌드 C/c + + 코드](../build/building-on-the-command-line.md)합니다.  
  
     컴퓨터 운영 체제 및 구성에 따라 코드를 정상적으로 컴파일하려면 관리자 자격 증명이 필요할 수 있습니다. 명령 프롬프트 창을 관리자 권한으로을 실행 하려면에 대 한 바로 가기 메뉴를 열고 **개발자 명령 프롬프트** 선택한 후 **관리자 권한으로 실행**합니다.  
  
2.  명령 프롬프트에서 다음을 입력 **메모장 basiccx.cpp**합니다.  
  
     선택 **예** 때 메시지가 표시 되는 파일을 만듭니다.  
  
3.  메모장에 다음 줄을 입력합니다.  
  
    ```cpp  
    using namespace Platform;  
  
    int main(Platform::Array<Platform::String^>^ args)  
    {  
        Platform::Details::Console::WriteLine("This is a C++/CX program.");  
    }  
  
    ```  
  
4.  메뉴 모음에서 **파일**, **저장**합니다.  
  
     Windows 런타임을 사용 하는 Visual c + + 소스 파일을 만든 [Platform 네임 스페이스](../cppcx/platform-namespace-c-cx.md) 네임 스페이스입니다.  
  
5.  명령 프롬프트에서 다음을 입력 **cl /EHsc /ZW basiccx.cpp /link /SUBSYSTEM:CONSOLE**합니다. cl.exe 컴파일러는 이 소스 파일을 .obj 파일로 컴파일한 다음 링커를 실행하여 실행 프로그램인 basiccx.exe를 생성합니다. (의 [/EHsc](../build/reference/eh-exception-handling-model.md) c + + 예외 처리 모델을 지정 하는 컴파일러 옵션 및 [/link](../build/reference/link-pass-options-to-linker.md) 플래그는 콘솔 응용 프로그램을 지정 합니다.)  
  
6.  Basiccx.exe 프로그램을 명령 프롬프트에서를 실행 하려면 입력 **basiccx**합니다.  
  
     프로그램이 다음 텍스트를 표시하고 종료됩니다.  
  
    ```Output  
    This is a C++/CX program.  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [C + + 언어 참조](../cpp/cpp-language-reference.md)   
 [C/C++ 프로그램 빌드](../build/building-c-cpp-programs.md)   
 [컴파일러 옵션](../build/reference/compiler-options.md)