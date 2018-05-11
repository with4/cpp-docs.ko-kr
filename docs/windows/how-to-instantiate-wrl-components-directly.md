---
title: '방법: 직접 WRL 구성 요소를 인스턴스화 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: 1a9fa011-0cee-4abf-bf83-49adf53ff906
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 127a8430e79e7963ea94646f70179df2f30450ff
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="how-to-instantiate-wrl-components-directly"></a>방법: 직접 WRL 구성 요소 인스턴스화
Windows 런타임 c + + 템플릿 라이브러리 (WRL)를 사용 하는 방법에 알아봅니다[Microsoft::WRL::Make](../windows/make-function.md) 및 [Microsoft::WRL::Details::MakeAndInitialize](../windows/makeandinitialize-function.md) 모듈에서 구성 요소를 인스턴스화하는 함수는 정의 합니다.  
  
 구성 요소를 직접 인스턴스화하고 때 줄일 수 있습니다 오버 헤드가 클래스 팩터리 또는 다른 메커니즘은 필요 하지 않습니다. 구성 요소 모두 유니버설 Windows 플랫폼 앱 및 데스크톱 앱에서 직접 인스턴스화할 수 있습니다.  
  
참조를 클래식 COM 구성 요소를 만들고 외부 데스크톱 응용 프로그램에서 인스턴스화할 Windows 런타임 c + + 템플릿 라이브러리를 사용 하는 방법을 알아보려면 [하는 방법: 클래식 COM 구성 요소 만들기](../windows/how-to-create-a-classic-com-component-using-wrl.md)합니다.  
  
 이 문서에서는 두 가지 예를 보여 줍니다. 사용 하 여 첫 번째 예제는 `Make` 구성 요소를 인스턴스화하는 함수입니다. 사용 하 여 두 번째 예제는 `MakeAndInitialize` 를 생성 하는 동안 실패할 수 있는 구성 요소를 인스턴스화하는 함수입니다. (COM 일반적으로 사용 하기 때문에 `HRESULT` 오류를 나타내지만 예외 대신 값 COM 형식이 일반적으로 throw 하지 않는 해당 생성자에서 합니다. `MakeAndInitialize` 있습니다. 해당 생성 인수를 통해 유효성을 검사 하는 구성 요소는 `RuntimeClassInitialize` 메서드.) 두 예제 모두 기본로 거 인터페이스를 정의 하 고 콘솔에 메시지를 작성 하는 클래스를 정의 하 여 해당 인터페이스를 구현 합니다.  
  
> [!IMPORTANT]
>  사용할 수 없습니다는 `new` 를 Windows 런타임 c + + 템플릿 라이브러리 구성 요소를 인스턴스화하는 연산자입니다. 항상 사용 하는 권장 따라서 `Make` 또는 `MakeAndInitialize` 구성 요소를 직접 인스턴스화할 수 있습니다.  
  
### <a name="to-create-and-instantiate-a-basic-logger-component"></a>만들고 기본로 거 구성 요소의 인스턴스  
  
1.  Visual Studio에서 만듭니다는 **Win32 콘솔 응용 프로그램** 프로젝트. 예를 들어 프로젝트 이름을 `WRLLogger`합니다.  
  
2.  추가 **Midl 파일 (.idl)** 프로젝트에 파일, 파일 이름을 `ILogger.idl`,이 코드를 추가 합니다.  
  
     [!code-cpp[wrl-logger-make#1](../windows/codesnippet/CPP/how-to-instantiate-wrl-components-directly_1.idl)]  
  
3.  다음 코드를 사용 하 여 WRLLogger.cpp의 내용을 바꿉니다.  
  
     [!code-cpp[wrl-logger-make#2](../windows/codesnippet/CPP/how-to-instantiate-wrl-components-directly_2.cpp)]  
  
### <a name="to-handle-construction-failure-for-the-basic-logger-component"></a>기본로 거 구성 요소에 대 한 생성 실패를 처리 하려면  
  
1.  정의를 바꾸려면 다음 코드를 사용 하 여 `CConsoleWriter` 클래스입니다. 이 버전 보유 개인 문자열 멤버 변수와 재정의 `RuntimeClass::RuntimeClassInitialize` 메서드. `RuntimeClassInitialize` 실패에 대 한 호출 `SHStrDup` 실패 합니다.  
  
     [!code-cpp[wrl-logger-makeandinitialize#1](../windows/codesnippet/CPP/how-to-instantiate-wrl-components-directly_3.cpp)]  
  
2.  다음 코드를 사용 하 여의 정의를 바꾸려면 `wmain`합니다. 이 버전은 사용 `MakeAndInitialize` 를 인스턴스화하는 `CConsoleWriter` 개체 및 검사는 `HRESULT` 결과입니다.  
  
     [!code-cpp[wrl-logger-makeandinitialize#2](../windows/codesnippet/CPP/how-to-instantiate-wrl-components-directly_4.cpp)]  
  
## <a name="see-also"></a>참고 항목  
 [Windows 런타임 c + + 템플릿 라이브러리 (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)   
 [Microsoft::WRL::Make](../windows/make-function.md)   
 [Microsoft::WRL::Details::MakeAndInitialize](../windows/makeandinitialize-function.md)