---
title: "방법: 직접 WRL 구성 요소 인스턴스화 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: 1a9fa011-0cee-4abf-bf83-49adf53ff906
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 직접 WRL 구성 요소 인스턴스화
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] \([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\) [Microsoft::WRL::Make](../windows/make-function.md) 및 [Microsoft::WRL::Details::MakeAndInitialize](../windows/makeandinitialize-function.md) 함수를 사용하여 구성 요소를 정의하는 모듈의 구성 요소를 인스턴스화 하는 방법을 알아봅니다.  
  
 구성 요소를 직접 인스턴스화하고 줄임으로서 클래스 팩터리 또는 다른 메커니즘이 필요하지 않을 때 오버헤드를 줄일 수 있습니다.   [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 응용 프로그램 및 데스크톱 응용 프로그램에서 구성 요소를 직접 인스턴스화할 수 있습니다  
  
 기본 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 구성 요소를 생성하고 외부 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] 응용 프로그램으로 부터 구성 요소를 인스턴스화 하기 위해 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 를 사용하는 자세한 방법은 [연습: 기본 Windows Runtime 구성 요소 만들기](../windows/walkthrough-creating-a-basic-windows-runtime-component-using-wrl.md) 를 참조하십시오.  클래식 COM 구성 요소를 만들고 외부 데스크톱 응용 프로그램으로부터 구성 요소를 인스턴스화하기 위해 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 를 사용하는 자세한 방법은 [방법: 기본 COM 구성 요소 만들기](../windows/how-to-create-a-classic-com-component-using-wrl.md) 를 참조하십시오.  
  
 이 문서는 두 가지 예를 보여 줍니다.  첫 번째 예제는 `Make` 함수를 사용하여 구성 요소를 인스턴스화 합니다.  두 번째 예제는 `MakeAndInitialize` 함수를 사용하여 구성하는 동안에 실패 할 수 있는 구성 요소를 인스턴스화 합니다. \(일반적으로 COM은 오류를 나타내기 위해 예외 대신 `HRESULT` 값을 사용하기 때문에 COM 형식은 일반적으로 해당 생성자로부터 throw 하지 않습니다.  `MakeAndInitialize` 는 `RuntimeClassInitialize` 메서드를 통해 구성요소가 해당 구성 인수의 유효성을 검사 할 수 있도록 합니다. 두 예제 모두기본 로거 인터페이스를 정의하고 콘솔에 메시지를 작성하는 클래스를 정의하여 해당 인터페이스를 구현 합니다.  
  
> [!IMPORTANT]
>  [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] 구성 요소를 인스턴스화 하기 위해 `new` 연산자를 사용할 수 없습니다.  따라서 구성 요소를 직접 인스턴스화하기 위해서는 `Make` 또는 `MakeAndInitialize` 를 사용하는 것이 좋습니다.  
  
### 기본 로거 구성 요소를 만들고 인스턴스화 하려면  
  
1.  Visual Studio 에서 **Win32 Console Application** 프로젝트를 만듭니다.  프로젝트 이름을 지정합니다. 예를들어 `WRLLogger`  
  
2.  프로젝트에 **Midl File \(.idl\)** 파일을 추가하고, 파일 이름을 `ILogger.idl` 로 지정합니다. 그리고 아래의 코드를 추가합니다.  
  
     [!code-cpp[wrl-logger-make#1](../windows/codesnippet/CPP/how-to-instantiate-wrl-components-directly_1.idl)]  
  
3.  WRLLogger.cpp 의 내용을 바꾸기 위해 아래의 코드를 사용합니다.  
  
     [!code-cpp[wrl-logger-make#2](../windows/codesnippet/CPP/how-to-instantiate-wrl-components-directly_2.cpp)]  
  
### 기본 로거 구성 요소에 대해 구문 오류를 처리하려면  
  
1.  `CConsoleWriter` 클래스의 정의를 바꾸려면 아래의 코드를 사용합니다.  이 버전은 private 문자열 멤버 변수를 보유하고 `RuntimeClass::RuntimeClassInitialize` 메서드를 오버라이드 합니다.   `SHStrDup` 에 대한 호출이 실패하면 `RuntimeClassInitialize` 도 실패합니다.  
  
     [!code-cpp[wrl-logger-makeandinitialize#1](../windows/codesnippet/CPP/how-to-instantiate-wrl-components-directly_3.cpp)]  
  
2.  `wmain` 의 정의를 바꾸려면 아래의 코드를 사용하십시오.  이 버전은 `CConsoleWriter` 개체를 인스턴스화하고 `HRESULT` 결과를 검사하기 위해 `MakeAndInitialize` 를 사용합니다.  
  
     [!code-cpp[wrl-logger-makeandinitialize#2](../windows/codesnippet/CPP/how-to-instantiate-wrl-components-directly_4.cpp)]  
  
## 참고 항목  
 [Windows 런타임 C\+\+ 템플릿 라이브러리\(WRL\)](../windows/windows-runtime-cpp-template-library-wrl.md)   
 [Microsoft::WRL::Make](../windows/make-function.md)   
 [Microsoft::WRL::Details::MakeAndInitialize](../windows/makeandinitialize-function.md)