---
title: "형식 및 멤버가 사용되지 않도록 지정(C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b20b01c1-a439-4ff0-8cf3-d7280c492813
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# 형식 및 멤버가 사용되지 않도록 지정(C++/CX)
C\+\+\/CX에서는 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 특성을 사용한 생산자와 소비자의 [Deprecated](http://msdn.microsoft.com/ko-kr/8b02ad36-3b5f-4361-888b-e6a99040e57c) 형식 및 멤버의 선언이 지원됩니다. 이 속성이 적용된 API를 사용하는 경우 API가 더 이상 사용되지 않음을 나타내고 대체 API를 사용하도록 권장하는 컴파일 타임 경고 메시지가 나타납니다. public 형식 및 메서드에서 이 특성을 적용하고 사용자 지정 메시지를 제공할 수 있습니다.  
  
> [!CAUTION]
>  [Deprecated](http://msdn.microsoft.com/ko-kr/8b02ad36-3b5f-4361-888b-e6a99040e57c) 특성은 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 형식에서만 사용할 수 있습니다. 표준 C\+\+ 클래스 및 멤버에는 [\_\_declspec\(deprecated\)](http://msdn.microsoft.com/library/044swk7y.aspx)를 사용하세요.  
  
## 예제  
 다음 예제에서는 Windows 런타임 구성 요소에서 사용자 고유의 공용 API를 사용할 수 없게 하는 방법을 보여 줍니다.[Windows:Foundation::Metadata::DeprecationType](http://msdn.microsoft.com/ko-kr/ee01e63d-37d0-4273-accc-fca174f88bfa) 형식의 두 번째 매개 변수는 API를 사용할 수 없게 할지 제거할지 여부를 지정합니다. 현재는 DeprecationType::Deprecated 값만 지원됩니다. 특성의 세 번째 매개 변수는 특성이 적용되는 [Windows::Foundation::Metadata::Platform](http://msdn.microsoft.com/ko-kr/1eae292d-1ab7-4d97-a58c-b0beffd51ef5)을 지정합니다.  
  
```  
  
namespace wfm = Windows::Foundation::Metadata; public ref class Bicycle sealed { public: property double Speed; [wfm::Deprecated("Use the Speed property to compute the angular speed of the wheel", wfm::DeprecationType::Deprecate, 0x0)] double ComputeAngularVelocity(); };  
```  
  
## 지원되는 대상  
 다음 표에서는 Deprecated 특성이 적용될 수 있는 구문을 보여 줍니다.  
  
||  
|-|  
|XAML 컨트롤|  
|대리자\(delegate\)|  
|이벤트\(event\)|  
|열거형 필드|  
|enum|  
|struct|  
|메서드|  
|클래스|  
|interface\(인터페이스\)|  
|속성|  
|구조체 필드|  
|매개 변수가 있는 생성자|  
  
## 참고 항목  
 [형식 시스템](../cppcx/type-system-c-cx.md)   
 [Visual C\+\+ 언어 참조](../cppcx/visual-c-language-reference-c-cx.md)   
 [네임스페이스 참조](../cppcx/namespaces-reference-c-cx.md)