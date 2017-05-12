---
title: "스레딩 및 마샬링(C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4451"
helpviewer_keywords: 
  - "스레딩 문제, C++/CX"
  - "민첩성, C++/CX"
  - "C++/CX, 스레딩 문제"
ms.assetid: 83e9ca1d-5107-4194-ae6f-e01bd928c614
caps.latest.revision: 17
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 17
---
# 스레딩 및 마샬링(C++/CX)
대부분의 경우 표준 C\+\+ 개체와 같은 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 클래스 인스턴스는 어떠한 스레드에서도 액세스될 수 있습니다. 이러한 클래스를 "agile"이라고 합니다. 그러나 Windows에 제공되는 적은 수의 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 클래스는 agile이 아니며 표준 C\+\+ 개체보다는 COM 개체처럼 사용되어야 합니다. agile이 아닌 클래스를 사용하기 위해 COM 전문가일 필요는 없지만 클래스의 스레딩 모델과 마샬링 동작을 고려해야 합니다. 이 문서에서는 agile이 아닌 클래스의 인스턴스를 사용해야 하는 드문 경우에 대한 배경 정보와 지침을 제공합니다.  
  
## 스레딩 모델 및 마샬링 동작  
 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 클래스는 적용된 두 가지 특성에 표시된 대로 다양한 방법으로 동시 스레드 액세스를 지원할 수 있습니다.  
  
-   `ThreadingModel` 특성에는 `ThreadingModel` 열거형으로 정의된 STA, MTA 또는 Both 값 중 하나가 사용될 수 있습니다.  
  
-   `MarshallingBehavior` 특성에는 `MarshallingType` 열거형으로 정의된 Agile, None 또는 Standard 값 중 하나가 사용될 수 있습니다.  
  
 `ThreadingModel` 특성은 활성화될 때 클래스가 로드되는 컨텍스트\(사용자 인터페이스 스레드\(STA\) 컨텍스트에서만, 백그라운드 스레드\(MTA\) 컨텍스트에서만 또는 개체를 만드는 스레드\(Both\)의 컨텍스트에서\)를 지정합니다.`MarshallingBehavior` 특성 값은 다양한 스레딩 컨텍스트에서 개체가 동작하는 방식을 나타냅니다. 대부분의 경우에는 이러한 값에 대해 자세히 이해할 필요가 없습니다.  Windows API에서 제공하는 클래스 중 약 90%가 `ThreadingModel`\=Both 및 `MarshallingType`\=Agile을 사용합니다. 따라서 하위 수준의 스레딩 세부 사항을 투명하고 효율적으로 처리할 수 있습니다.`ref new`를 사용하여 "agile" 클래스를 만드는 경우 기본 응용 프로그램 스레드 또는 하나 이상의 작업자 스레드에서 이에 대한 메서드를 호출할 수 있습니다.  즉, Windows나 타사에서 제공하는 모든 agile 클래스를 코드의 어느 위치에나 사용할 수 있습니다. 클래스의 스레딩 모델이나 마샬링 동작은 신경 쓸 필요가 없습니다.  
  
## [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 구성 요소 사용  
 [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] 응용 프로그램을 만들 때는 agile 및 agile이 아닌 구성 요소 모두와 상호 작용할 수도 있습니다. agile이 아닌 구성 요소와 상호 작용할 때는 다음과 같은 경고가 나타날 수 있습니다.  
  
### agile이 아닌 클래스를 사용할 때 발생하는 컴파일러 경고\(C4451\)  
 일부 클래스는 여러 가지 이유로 인해 agile이 될 수 없습니다. 사용자 인터페이스 스레드와 백그라운드 스레드 모두에서 agile이 아닌 클래스의 인스턴스에 액세스하는 경우 런타임에 올바른 동작을 보장하기 위해 특별히 주의를 기울여야 합니다. 응용 프로그램의 agile이 아닌 런타임 클래스를 전역 범위에서 인스턴스화하거나 agile이 아닌 형식을 그 자체가 agile로 표시된 ref 클래스의 클래스 멤버로 선언하면 Visual C\+\+ 컴파일러에서 경고를 발생시킵니다.  
  
 agile이 아닌 클래스 중 가장 처리하기 쉬운 것은 `ThreadingModel`\=Both 및 `MarshallingType`\=Standard를 사용하는 클래스입니다.`Agile<T>` 도우미 클래스를 사용하기만 하면 이러한 클래스를 agile로 만들 수 있습니다.   다음 예제에서는 `Windows::Security::Credentials::UI::CredentialPickerOptions^` 형식의 agile이 아닌 개체 선언과 그 결과로 실행된 컴파일러 경고를 보여줍니다.  
  
```  
  
ref class MyOptions  
    {  
    public:  
        property Windows::Security::Credentials::UI::CredentialPickerOptions^ Options  
  
        {  
            Windows::Security::Credentials::UI::CredentialPickerOptions^ get()   
            {  
                return _myOptions;  
            }  
        }  
    private:  
        Windows::Security::Credentials::UI::CredentialPickerOptions^ _myOptions;  
    };  
```  
  
 실행된 경고는 다음과 같습니다.  
  
> `Warning 1 warning C4451: 'Platform::Agile<T>::_object' : Usage of ref class 'Windows::Security::Credentials::UI::CredentialPickerOptions' inside this context can lead to invalid marshaling of object across contexts. Consider using 'Platform::Agile<Windows::Security::Credentials::UI::CredentialPickerOptions>' instead`  
  
 "Standard"의 마샬링 동작이 있는 개체에 멤버 범위 또는 전역 범위에서 참조를 추가하면 컴파일러가 `Platform::Agile<T>`: `Consider using 'Platform::Agile<Windows::Security::Credentials::UI::CredentialPickerOptions>' instead`와 같이 형식을 래핑하라는 경고를 실행합니다. `Agile<T>`를 사용하면 클래스를 다른 모든 agile 클래스처럼 사용할 수 있습니다.`Platform::Agile<T>`은 이러한 경우에 사용하세요.  
  
-   agile이 아닌 변수가 전역 범위에 선언되었습니다.  
  
-   agile이 아닌 변수가 클래스 범위에 선언되었고 사용하는 코드가 포인터를 올바른 마샬링 없이 다른 아파트에서 사용하는 밀수 가능성이 있습니다.  
  
 이러한 조건 중 어느 것도 해당하지 않는 경우 포함하는 클래스를 agile이 아닌 것으로 표시할 수 있습니다. 즉, Agile이 아닌 클래스에서만 Agile이 아닌 개체를 직접 보유하고 Agile 클래스에서는 Platform::Agile\<T\>을 통해 Agile이 아닌 개체를 보유해야 합니다.  
  
 다음 예제에서는 경고를 안전하게 무시할 수 있도록 `Agile<T>`을 사용하는 방법을 보여 줍니다.  
  
```  
  
#include <agile.h>  
ref class MyOptions  
    {  
    public:  
        property Windows::Security::Credentials::UI::CredentialPickerOptions^ Options  
  
        {  
            Windows::Security::Credentials::UI::CredentialPickerOptions^ get()   
            {  
                return m_myOptions.Get();  
            }  
        }  
    private:  
        Platform::Agile<Windows::Security::Credentials::UI::CredentialPickerOptions^> m_myOptions;  
  
    };  
  
```  
  
 `Agile`은 ref 클래스에 반환 값 또는 매개 변수로 전달할 수 없습니다.`Agile<T>::Get()` 메서드는 ABI\(응용 프로그램 이진 인터페이스\) 너머로 공용 메서드 또는 속성에 전달할 수 있는 개체 핸들\(^\)을 반환합니다.  
  
 Visual C\+\+에서는 마샬링 동작이 "None"인 in\-proc [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 클래스에 대한 참조를 만들 때 컴파일러가 경고 C4451을 실행하지만 `Platform::Agile<T>` 사용을 고려하도록 제안하는 것은 아닙니다.  컴파일러는 이러한 경고 이외에 다른 지원을 제공할 수 없으므로 클래스를 올바르게 사용하고 코드가 STA 구성 요소를 사용자 인터페이스 스레드에서만 호출하고, MTA 구성 요소를 백그라운드 스레드에서만 호출하도록 하는 것은 사용자의 책임입니다.  
  
## agile [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 구성 요소 작성  
 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]에 ref 클래스를 정의하면 기본적으로 agile입니다. 즉, `ThreadingModel`\=Both 및 `MarshallingType`\=Agile이 있습니다.[!INCLUDE[cppwrl](../cppcx/includes/cppwrl-md.md)]를 사용하는 경우 `FtmBase`를 사용하는 `FreeThreadedMarshaller`에서 파생하여 클래스를 agile로 만들 수 있습니다.`ThreadingModel`\=Both 또는 `ThreadingModel`\=MTA가 있는 클래스를 작성하는 경우 클래스가 스레드로부터 안전한지 확인하세요. 자세한 내용은 [개체 만들기 및 사용\(WRL\)](http://msdn.microsoft.com/ko-kr/d5e42216-e888-4f1f-865a-b5ccd0def73e)을 참조하세요.  
  
 사용자는 ref 클래스의 스레딩 모델 및 마샬링 동작을 수정할 수 있습니다. 그러나 클래스를 agile이 아닌 것으로 렌더링하는 변경 작업을 수행하는 경우 이러한 변경 사항과 관련된 영향을 알고 있어야 합니다.  
  
 다음 예제에서는 `MarshalingBehavior` 클래스 라이브러리의 런타임 클래스에 `ThreadingModel` 및 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 특성을 적용하는 방법을 보여 줍니다. 응용 프로그램이 DLL을 사용하고 `ref new` 키워드를 사용하여 `MySTAClass` 클래스 개체를 활성화하면 개체가 단일 스레드 아파트에서 활성화되고 마샬링을 지원하지 않습니다.  
  
```  
using namespace Windows::Foundation::Metadata;  
using namespace Platform;  
  
[Threading(ThreadingModel::STA)]  
[MarshalingBehavior(MarshalingType::None)]   
public ref class MySTAClass  
{  
};  
  
```  
  
 unsealed 클래스에는 컴파일러가 파생된 클래스의 이러한 특성 값이 동일한지 확인할 수 있도록 마샬링 및 스레딩 특성 설정이 있어야 합니다. 클래스에 이러한 설정이 명시적으로 지정되지 않은 경우 컴파일러가 오류를 생성하고 컴파일에 실패합니다. unsealed 클래스에서 파생된 클래스는 다음과 같은 경우 컴파일러 오류를 생성합니다.  
  
-   파생된 클래스에 `ThreadingModel` 및 `MarshallingBehavior` 특성이 정의되어 있지 않습니다.  
  
-   파생된 클래스의 `ThreadingModel` 및 `MarshallingBehavior` 특성 값이 기본 클래스와 일치하지 않습니다.  
  
 타사 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 구성 요소에 필요한 스레딩 및 마샬링 정보는 구성 요소의 응용 프로그램 매니페스트 등록 정보에 지정됩니다. 모든 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 구성 요소를 agile로 만드는 것이 좋습니다. 이렇게 하면 클라이언트 코드가 응용 프로그램의 모든 스레드에서 구성 요소를 호출할 수 있고 마샬링이 없는 직접 호출이므로 이러한 호출의 성능이 개선됩니다. 이와 같은 방식으로 클래스를 작성하면 클라이언트 코드가 `Platform::Agile<T>`로 클래스를 사용할 필요가 없습니다.  
  
## 참고 항목  
 [\(NOTINBUILD\) 고급 항목](http://msdn.microsoft.com/ko-kr/1ccff0cf-a6cc-47ef-a05f-eba6307b3ced)   
 [ThreadingModel](http://msdn.microsoft.com/library/windows/apps/xaml/windows.foundation.metadata.threadingmodel.aspx)   
 [MarshallingBehavior](http://msdn.microsoft.com/library/windows/apps/xaml/windows.foundation.metadata.marshalingbehaviorattribute.aspx)