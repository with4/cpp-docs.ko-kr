---
title: '방법: WRL을 사용 하 여 Windows 런타임 구성 요소를 사용 하 고 활성화 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: 54828f02-6af3-45d1-b965-d0104442f8d5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 50c37438bf3a840f57119245b845d0b94f1873db
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="how-to-activate-and-use-a-windows-runtime-component-using-wrl"></a>방법: WRL을 사용하여 Windows 런타임 구성 요소 활성화 및 사용
이 문서에서는 Windows 런타임 c + + 템플릿 라이브러리 (WRL)를 사용 하 여 Windows 런타임을 초기화 하는 방법과 활성화 하 고 Windows 런타임 구성 요소를 사용 하는 방법을 보여 줍니다.  
  
 구성 요소를 사용 하려면 구성 요소에 의해 구현 되는 형식에 대 한 인터페이스 포인터를 획득 해야 합니다. 및의 Windows 런타임이 기본 기술 구성 요소 개체 모델 (COM) 이기 때문에 형식의 인스턴스를 유지 하기 위해 COM 규칙을 따라야 합니다. 예를 들어 유지 해야 합니다는 *참조 횟수* 결정 하는 메모리에서 유형을 삭제 하는 경우.  
  
 Windows 런타임 c + + 템플릿 라이브러리를 간소화 하기 위해 Windows 런타임을 사용 스마트 포인터 서식 파일을 제공 [ComPtr\<T >](../windows/comptr-class.md), 참조 횟수를 자동으로 수행 합니다. 변수를 선언할 때 지정 `ComPtr<` *인터페이스 이름이* `>` *식별자*합니다. 인터페이스 멤버에 액세스 하려면 화살표 멤버 액세스 연산자를 적용할 (`->`) 식별자입니다.  
  
> [!IMPORTANT]
>  인터페이스 함수를 호출 하면 항상 테스트는 `HRESULT` 값을 반환 합니다.  
  
## <a name="activating-and-using-a-windows-runtime-component"></a>활성화 하 고 Windows 런타임 구성 요소를 사용 하 여  
 다음 단계를 사용 하 여는 `Windows::Foundation::IUriRuntimeClass` 인터페이스를 Windows 런타임 구성 요소에 대 한 활성화 팩터리를 만들어 해당 구성의 인스턴스를 만들고, 속성 값을 검색 하는 방법을 보여 줍니다. 또한 Windows 런타임을 초기화 하는 방법을 보여 줍니다. 전체 예제와 같습니다.  
  
> [!IMPORTANT]
>  일반적으로 유니버설 Windows 플랫폼 (UWP) 응용 프로그램에서 Windows 런타임 c + + 템플릿 라이브러리를 사용 되지만이 예제에 대 한 예시는 콘솔 응용 프로그램을 사용 합니다. 와 같은 함수가 `wprintf_s` 는 UWP 앱에서 사용할 수 없습니다. 형식 및 UWP 앱에서 사용할 수 있는 함수에 대 한 자세한 내용은 참조 [CRT 함수는 유니버설 Windows 플랫폼 앱에서 지원 되지 않습니다](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) 및 [UWP 앱 용 Win32 및 COM](/uwp/win32-and-com/win32-and-com-for-uwp-apps)합니다.  
  
#### <a name="to-activate-and-use-a-windows-runtime-component"></a>활성화 하 고 Windows 런타임 구성 요소를 사용 하 여  
  
1.  포함 (`#include`) Windows 런타임, Windows 런타임 c + + 템플릿 라이브러리 또는 c + + 표준 라이브러리 헤더 필수입니다.  
  
     [!code-cpp[wrl-consume-component#2](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_1.cpp)]  
  
     .cpp 파일의 `using namespace` 지시문을 활용하여 코드를 보다 읽기 쉽게 만드는 것이 좋습니다.  
  
2.  앱이 실행 되는 스레드를 초기화 합니다. 모든 앱은 해당 스레드 및 스레딩 모델 초기화 해야 합니다. 사용 하 여이 예제는 [Microsoft::WRL::Wrappers::RoInitializeWrapper](../windows/roinitializewrapper-class.md) 클래스는 Windows 런타임을 초기화를 하 고 지정 [RO_INIT_MULTITHREADED](http://msdn.microsoft.com/library/windows/apps/br224661.aspx) 스레딩 모델로 합니다. `RoInitializeWrapper` 클래스가 호출 `Windows::Foundation::Initialize` 생성 시 및 `Windows::Foundation::Uninitialize` 때 소멸 됩니다.  
  
     [!code-cpp[wrl-consume-component#3](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_2.cpp)]  
  
     두 번째 문에 [RoInitializeWrapper::HRESULT](../windows/roinitializewrapper-hresult-parens-operator.md) 연산자는 반환 된 `HRESULT` 를 호출 하 여 `Windows::Foundation::Initialize`합니다.  
  
3.  만들기는 *활성화 팩터리* 에 대 한는 `ABI::Windows::Foundation::IUriRuntimeClassFactory` 인터페이스입니다.  
  
     [!code-cpp[wrl-consume-component#4](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_3.cpp)]  
  
     Windows 런타임 정규화 된 이름을 사용 하 여 형식을 식별 합니다. `RuntimeClass_Windows_Foundation_Uri` 매개 변수는 Windows 런타임에서 제공 하 고 필요한 런타임 클래스 이름을 포함 하는 문자열입니다.  
  
4.  초기화는 [Microsoft::WRL::Wrappers::HString](../windows/hstring-class.md) URI를 나타내는 변수 `"http://www.microsoft.com"`합니다.  
  
     [!code-cpp[wrl-consume-component#6](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_4.cpp)]  
  
     Windows 런타임에서 Windows 런타임에서 사용 하는 문자열에 대 한 메모리를 할당 하지 않습니다. 대신, Windows 런타임 버퍼를 유지 관리 하 고 작업을 위해 사용 하 여를 다음 핸들을 반환 버퍼 자신이 만들어진 문자열의 복사본을 만듭니다.  
  
5.  사용 하 여는 `IUriRuntimeClassFactory::CreateUri` 를 만드는 팩터리 메서드입니다는 `ABI::Windows::Foundation::IUriRuntimeClass` 개체입니다.  
  
     [!code-cpp[wrl-consume-component#7](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_5.cpp)]  
  
6.  호출 된 `IUriRuntimeClass::get_Domain` 의 값을 검색 하는 메서드는 `Domain` 속성입니다.  
  
     [!code-cpp[wrl-consume-component#8](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_6.cpp)]  
  
7.  도메인 이름을 콘솔에 출력을 반환 합니다. 모든 `ComPtr` 및 RAII 개체는 범위를 벗어나면 자동으로 릴리스됩니다.  
  
     [!code-cpp[wrl-consume-component#9](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_7.cpp)]  
  
     [WindowsGetStringRawBuffer](http://msdn.microsoft.com/library/windows/apps/br224636.aspx) 함수 기본 유니코드 형식의 URI 문자열을 검색 합니다.  
  
 전체 예제는 다음과 같습니다.  
  
 [!code-cpp[wrl-consume-component#1](../windows/codesnippet/CPP/how-to-activate-and-use-a-windows-runtime-component-using-wrl_8.cpp)]  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 코드를 컴파일하려면 코드를 복사 하 고 다음 Visual Studio 프로젝트에 붙여 하거나 라는 파일에 붙여 `wrl-consume-component.cpp` 후 Visual Studio 명령 프롬프트 창에서 다음 명령을 실행 합니다.  
  
 **cl.exe wrl-consume-component.cpp runtimeobject.lib**  
  
## <a name="see-also"></a>참고 항목  
 [Windows 런타임 C++ 템플릿 라이브러리(WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)