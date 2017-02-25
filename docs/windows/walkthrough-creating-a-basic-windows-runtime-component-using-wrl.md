---
title: "연습: WRL을 사용하여 기본 Windows 런타임 구성 요소 만들기 | Microsoft Docs"
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
ms.assetid: 6e3f0986-7905-4f94-90e5-22c2ebfc8cd0
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# 연습: WRL을 사용하여 기본 Windows 런타임 구성 요소 만들기
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

이 문서에서는 사용 하는 방법을 보여 줍니다.는 [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] ([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)])를 만드는 기본 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 구성 요소입니다. 구성 요소는 두 개의 숫자를 추가 하 고 결과 소수 때 이벤트를 발생 시킵니다. 이 문서에서 구성 요소를 사용 하는 방법을 보여 줍니다는 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] JavaScript를 사용 하는 응용 프로그램입니다.  
  
## <a name="prerequisites"></a>필수 조건  
  
-   에 대 한 경험에서 [Windows 런타임](http://msdn.microsoft.com/library/windows/apps/br211377.aspx)합니다.  
  
-   COM 경험  
  
### <a name="to-create-a-basic-includewrttokenwrtmdmd-component-that-adds-two-numbers"></a>기본 키를 만들려면 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 두 숫자를 추가 하는 구성 요소  
  
1.  Visual Studio에서 Visual c + + 만듭니다 `WRLClassLibrary` 프로젝트입니다. 문서 [클래스 라이브러리 프로젝트 템플릿](../windows/wrl-class-library-project-template.md) 서식이 파일을 다운로드 하는 방법을 설명 합니다. 프로젝트 이름을 `Contoso`로 지정합니다.  
  
2.  Contoso.cpp 및 Contoso.idl "Calculator"와 "WinRTClass"의 모든 인스턴스를 대체 합니다.  
  
3.  Contoso.idl, 추가 `Add` 메서드는 `ICalculator` 인터페이스입니다.  
  
     [!code-cpp[wrl-basic-component#1](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_1.idl)]  
  
4.  Contoso.cpp, 추가 `Add` 메서드를는 `public` 의 섹션은 `Calculator` 클래스입니다.  
  
     [!code-cpp[wrl-basic-component#2](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_2.cpp)]  
  
    > [!IMPORTANT]
    >  사용 해야 하는 COM 구성 요소를 만드는 때문에 `__stdcall` 호출 규칙입니다.  
  
     사용 하는 것이 좋습니다 `_Out_` 및 함수 매개 변수를 사용 하는 방법을 설명 하는 다른 소스 주석 SAL (언어) 주석입니다. SAL 주석은 반환 값도 설명합니다. SAL 주석 사용는 [C/c + + 코드 분석 도구](../Topic/Code%20Analysis%20for%20C-C++%20Overview.md) 결함 C 및 c + + 소스 코드를 검색 합니다. 도구에서 보고 되는 일반적인 코딩 오류는 버퍼 오버런, 초기화 되지 않은 메모리를 포함 하 고 null 포인터 역참조, 메모리 및 리소스 누수 합니다.  
  
### <a name="to-use-the-component-from-a-includewin8appnamelongtokenwin8appnamelongmdmd-app-that-uses-javascript"></a>구성 요소를 사용 하는 [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] JavaScript를 사용 하는 응용 프로그램  
  
1.  Visual Studio에서 새로운 JavaScript 추가 `Blank App` 에 프로젝트는 `Contoso` 솔루션입니다. 프로젝트 이름을 `CalculatorJS`로 지정합니다.  
  
2.  에 `CalculatorJS` 프로젝트에서에 대 한 참조를 추가 하는 `Contoso` 프로젝트입니다.  
  
3.  Default.html에서 대체는 `body` 이러한 UI 요소를 사용 하 여 섹션:  
  
     [!code-html[wrl-basic-component#3](../windows/codesnippet/Html/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_3.html)]  
  
4.  Default.js에서 구현 된 `OnClick` 함수입니다.  
  
     [!code-javascript[wrl-basic-component#4](../windows/codesnippet/JavaScript/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_4.js)]  
  
    > [!NOTE]
    >  JavaScript에서 메서드 이름의 첫 글자의 표준 명명 규칙을 일치 하도록 소문자로 변경 됩니다.  
  
### <a name="to-add-an-event-that-fires-when-a-prime-number-is-calculated"></a>최적 값을 계산할 때 발생 하는 이벤트를 추가 하려면  
  
1.  선언 이전에 Contoso.idl에서 `ICalculator`, 대리자 형식을 정의 `PrimeNumberEvent`, 를 제공 하는 `int` 인수입니다.  
  
     [!code-cpp[wrl-basic-component#5](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_5.idl)]  
  
     사용 하는 경우는 `delegate` MIDL 컴파일러 키워드를 포함 하는 인터페이스를 만듭니다는 `Invoke` 대리자의 시그니처와 일치 하는 메서드입니다. 생성 된 파일은이 예제에서는 Contoso_h.h 정의 `IPrimeNumberEvent` 이 절차의 뒷부분에서 사용 되는 인터페이스입니다.  
  
     [!code-cpp[wrl-basic-component#13](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_6.cpp)]  
  
2.  에 `ICalculator` 인터페이스를 정의 `PrimeNumberFound` 이벤트입니다.  `eventadd` 및 `eventremove` 특성을 지정 하는의 소비자는 `ICalculator` 인터페이스 구독할와이 이벤트에서 등록을 취소할 수 있습니다.  
  
     [!code-cpp[wrl-basic-component#6](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_7.idl)]  
  
3.  Contoso.cpp, 추가 된 `private` [Microsoft::WRL::EventSource](../windows/eventsource-class.md) 이벤트 구독자를 관리 하 고 이벤트 처리기가 호출 하는 멤버 변수입니다.  
  
     [!code-cpp[wrl-basic-component#7](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_8.cpp)]  
  
4.  Contoso.cpp, 구현에서 `add_PrimeNumberFound` 및 `remove_PrimeNumberFound` 메서드.  
  
     [!code-cpp[wrl-basic-component#8](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_9.cpp)]  
  
### <a name="to-raise-the-event-when-a-prime-number-is-calculated"></a>최적 값을 계산할 때 이벤트 발생  
  
1.  Contoso.cpp, 추가 `IsPrime` 메서드를는 `private` 의 섹션은 `Calculator` 클래스입니다.  
  
     [!code-cpp[wrl-basic-component#12](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_10.cpp)]  
  
2.  수정는 `Calculator`의 `Add` 메서드를 호출 하는 [Microsoft::WRL::EventSource::InvokeAll](../windows/eventsource-invokeall-method.md) 최적 값을 계산할 때 메서드.  
  
     [!code-cpp[wrl-basic-component#11](../windows/codesnippet/CPP/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_11.cpp)]  
  
### <a name="to-handle-the-event-from-javascript"></a>JavaScript에서 이벤트를 처리 하려면  
  
1.  Default.html에서 수정 된 `body` 소수 포함 하는 텍스트 영역을 포함 하도록 섹션입니다.  
  
     [!code-html[wrl-basic-component#9](../windows/codesnippet/Html/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_12.html)]  
  
2.  Default.js에서 수정 된 `Add` 를 처리 하는 함수는 `PrimeNumberFound` 이벤트입니다. 이벤트 처리기는 이전 단계에서 정의 된 텍스트 영역에는 소수를 추가 합니다.  
  
     [!code-javascript[wrl-basic-component#10](../windows/codesnippet/JavaScript/walkthrough-creating-a-basic-windows-runtime-component-using-wrl_13.js)]  
  
    > [!NOTE]
    >  JavaScript에서 이벤트 이름은 소문자으로 변경 되 고 "on"으로 표준 명명 규칙에 맞도록 앞에 추가 합니다.  
  
 다음 그림에서는 기본 계산기 응용 프로그램을 보여 줍니다.  
  
 ![JavaScript를 사용한 기본 계산기 응용 프로그램](../windows/media/wrl_basic_component.png "WRL_Basic_Component")  
  
## <a name="next-steps"></a>다음 단계  
  
## <a name="see-also"></a>참고 항목  
 [Windows 런타임 c + + 템플릿 라이브러리 (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md)   
 [클래스 라이브러리 프로젝트 템플릿](../windows/wrl-class-library-project-template.md)   
 [C/c + + 코드 분석 도구](../Topic/Code%20Analysis%20for%20C-C++%20Overview.md)