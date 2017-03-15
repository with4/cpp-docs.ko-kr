---
title: "방법: WRL을 사용하여 Windows 런타임 구성 요소 활성화 및 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: 54828f02-6af3-45d1-b965-d0104442f8d5
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# 방법: WRL을 사용하여 Windows 런타임 구성 요소 활성화 및 사용
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 문서는 어떻게 [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] \([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\) 를 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 을 초기화하는 데 사용하는지와 어떻게 활성화 하고 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 구성요소를 사용하는지를 보여줍니다.  
  
> [!NOTE]
>  이 예제는 내재된 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 구성요소를 활성화합니다.  비슷한 방법으로 활성화할 수 있는 구성 요소를 직접 만드는 방법에 대한 자세한 내용은 [연습: 기본 Windows Runtime 구성 요소 만들기](../windows/walkthrough-creating-a-basic-windows-runtime-component-using-wrl.md)를 참조하십시오.  
  
 구성요소를 사용하기 위하여, 구성요소에 의해 구현된 형식에 대한 인터페이스 포인터를 가져와야만 합니다.  [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 의 기본 기술은 구성요소 개체 모델\(COM\)이기 때문에, 형식의 인스턴스를 유지하기 위한 COM 규칙을 따라야만 합니다.  예를 들어, 메모리로부터 삭제된 형식을 결정하는 *참조 횟수* 를 유지해야만 합니다.  
  
 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 의 사용을 단순화하기 위하여, [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 는 스마트 포인터 템플릿과 자동으로 참조 횟수가 실행되는 [ComPtr\<T\>](../windows/comptr-class.md) 을 제공합니다.  변수를 선언할 때, `ComPtr<`*interface\-name*`>` *identifier*을 지정합니다.  인터페이스 멤버에 액세스 하려면 화살표 멤버 액세스 연산자를 \(`->`\) 식별자에 적용합니다.  
  
> [!IMPORTANT]
>  인터페이스 함수를 호출 하면 항상 테스트는 `HRESULT` 값을 반환 합니다.  
  
## Windows 런타임 구성 요소를 사용하여 활성화합니다.  
 다음 단계는 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 구성요소에 대한 정품인증 팩터리를 어떻게 만드는지 보여주기 위한 `Windows::Foundation::IUriRuntimeClass` 인터페이스를 사용합니다, 구성요소 인스턴스를 만들고 속성 값을 검색합니다.  또한 어떻게 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 를 초기화할지를 보여줍니다.  다음은 완성된 예제입니다.  
  
> [!IMPORTANT]
>  일반[!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 응용프로그램에서, [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 를 일반적으로 사용하더라도, 이 예제는 설명을 위해 콘솔 응용프로그램을 사용합니다.  `wprintf_s` 와 같은 함수는 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 응용프로그램으로부터 사용가능 하지 않습니다.  [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 응용프로그램에서 사용할 수 있는 형식과 함수에 대한 자세한 설명은, [\/ZW를 사용한 CRT 함수 를 지원하지 않습니다.](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx) 및 [윈도우 스토어 앱에 대한 Win32 및 COM](http://msdn.microsoft.com/library/windows/apps/br205757.aspx)을 참조하십시오.  
  
#### Windows 런타임 구성요소를 사용하고 활성화시킵니다.  
  
1.  모든 필수 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 또는 표준 C\+\+ 라이브러리 헤더를 포함\(`#include`\)합니다.  
  
     [!code-cpp[wrl-consume-component#2](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_1.cpp)]  
  
     .cpp 파일의 `using namespace` 지시문을 활용하여 코드를 보다 읽기 쉽게 만드는 것이 좋습니다.  
  
2.  응용 프로그램이 실행되는 스레드를 초기화합니다.  모든 응용 프로그램의 스레드 및 스레딩 모델로 초기화해야 합니다.  이 예제는 [Microsoft::WRL::Wrappers::RoInitializeWrapper](../windows/roinitializewrapper-class.md) 클래스를 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 을 초기화하기 위해 사용하고 [RO\_INIT\_MULTITHREADED](http://msdn.microsoft.com/library/windows/apps/br224661.aspx) 를 스레드 모델로서 지정합니다.  이 `RoInitializeWrapper` 클래스는 `Windows::Foundation::Initialize` 와 `Windows::Foundation::Uninitialize` 을 구조체에서 호출하는데, 이는 삭제될 때입니다.  
  
     [!code-cpp[wrl-consume-component#3](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_2.cpp)]  
  
     두 번째 명세서에서, 이 [RoInitializeWrapper::HRESULT](../windows/roinitializewrapper-hresult-parens-operator.md) 연산자를 `HRESULT` 으로 반환합니다. 이는 `Windows::Foundation::Initialize` 호출로 부터입니다.  
  
3.  `ABI::Windows::Foundation::IUriRuntimeClassFactory` 인터페이스에 대한 *정품인증 팩터리* 를 만듭니다.  
  
     [!code-cpp[wrl-consume-component#4](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_3.cpp)]  
  
     [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 정규화 된 이름을 사용하여 형식을 식별 합니다.  `RuntimeClass_Windows_Foundation_Uri` 매개 변수가 제공하는 문자열은 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 필요한 런타임 클래스 이름을 포함 합니다.  
  
4.  URI `"http://www.microsoft.com"` 을 나타내는 [Microsoft::WRL::Wrappers::HString](../windows/hstring-class.md) 변수를 초기화합니다.  
  
     [!code-cpp[wrl-consume-component#6](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_4.cpp)]  
  
     [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 에서, [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 를 사용할 문자열에 대한 메모리를 할당하지 않습니다.  대신에, [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 는 작업을 유지하고 사용하는 버퍼에서 문자열의 복사본을 만들고 만들어진 버퍼에서 핸들을 반환합니다.  
  
5.  `IUriRuntimeClassFactory::CreateUri` 팩터리 메서드를 `ABI::Windows::Foundation::IUriRuntimeClass` 개체를 만들기 위해 사용합니다.  
  
     [!code-cpp[wrl-consume-component#7](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_5.cpp)]  
  
6.  `IUriRuntimeClass::get_Domain` 메서드를 `Domain` 속성의 값을 검색하기 위해 호출합니다.  
  
     [!code-cpp[wrl-consume-component#8](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_6.cpp)]  
  
7.  도메인 이름을 콘솔에 출력하고 반환합니다.  모든 `ComPtr` 및 RAII 개체는 범위를 벗어나면 자동으로 릴리스됩니다.  
  
     [!code-cpp[wrl-consume-component#9](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_7.cpp)]  
  
     이 [WindowsGetStringRawBuffer](http://msdn.microsoft.com/library/windows/apps/br224636.aspx) 함수는 URI 문자열의 형식 기본 유니코드를 검색합니다.  
  
 전체 예제는 다음과 같습니다:  
  
 [!code-cpp[wrl-consume-component#1](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_8.cpp)]  
  
## 코드 컴파일  
 코드를 컴파일하기 위하여, 복사하고 그때 Visual Studio 프로젝트에서 복사합니다, 또는 `wrl-consume-component.cpp` 이름의 파일에서 복사하고 그때 Visual Studio 명령어 프롬트 창에서 다음 명령어를 실행합니다.  
  
 **cl.exe wrl\-consume\-component.cpp runtimeobject.lib**  
  
## 참고 항목  
 [Windows 런타임 C\+\+ 템플릿 라이브러리\(WRL\)](../windows/windows-runtime-cpp-template-library-wrl.md)