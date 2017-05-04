---
title: "CLR 통합(C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 76e213cf-2f3d-4181-b35b-9fd25d5b307c
caps.latest.revision: 10
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 10
---
# CLR 통합(C++/CX)
일부 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 형식은 CLR\(공용 언어 런타임\)을 기반으로 둔 언어 및 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]의 특수 처리를 받습니다. 이 문서에서는 한 언어의 여러 형식을 다른 언어에 매핑하는 방법을 설명합니다. 예를 들어 CLR은 Windows.Foundation.IVector를 System.Collections.IList에 매핑하고, Windows.Foundation.IMap를 System.Collections.IDictionary에 매핑합니다. 마찬가지로 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]는 특별히 Platform::Delegate and Platform::String과 같은 형식을 매핑합니다.  
  
## [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]을 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]에 매핑  
 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]가 Windows 메타데이터\(.winmd\) 파일을 읽을 때 컴파일러에서는 일반 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 네임스페이스 및 형식을 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] 네임스페이스 및 형식에 자동으로 매핑합니다. 예를 들어 숫자 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 형식 `UInt32`는 `default::uint32`에 자동으로 매핑됩니다.  
  
 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]는 여러 다른 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 형식을 **Platform** 네임스페이스에 매핑합니다. 예를 들어 읽기 전용 유니코드 텍스트 문자열을 나타내는 **Windows::Foundation** HSTRING 핸들은 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]`Platform::String` 클래스에 매핑됩니다.[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 작업이 오류 HRESULT를 반환하면 이 오류는 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]`Platform::Exception`에 매핑됩니다. 자세한 내용은 [Built\-in Types](http://msdn.microsoft.com/ko-kr/acc196fd-09da-4882-b554-6c94685ec75f)을 참조하세요.  
  
 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]는 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 네임스페이스의 특정 형식을 매핑하여 형식 기능을 향상합니다.[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]는 이들 형식에 대해 C\+\+에 관련되고 형식의 표준 .winmd 파일에서 사용할 수 없는 도우미 생성자 및 메서드를 제공합니다.  
  
 다음 목록에서는 새 생성자 및 도우미 메서드를 지원하는 값 구조체를 보여 줍니다. 구조체 초기화 목록을 사용하는 이전에 작성된 코드가 있으면 새로 추가된 생성자를 사용하도록 이를 변경합니다.  
  
 **Windows::Foundation**  
  
-   요소  
  
-   Rect  
  
-   크기  
  
 **Windows::UI**  
  
-   색  
  
 **Windows::UI::Xaml**  
  
-   CornerRadius  
  
-   기간  
  
-   GridLength  
  
-   Thickness  
  
 **Windows::UI::Xaml::Interop**  
  
1.  TypeName  
  
 **Windows::UI::Xaml::Media**  
  
-   행렬  
  
 **Windows::UI::Xaml::Media::Animation**  
  
-   KeyTime  
  
-   RepeatBehavior  
  
 **Windows::UI::Xaml::Media::Media3D**  
  
-   Matrix3D  
  
## CLR을 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]에 매핑  
 Visual C\+\+ 또는 C\# 컴파일러는 .winmd 파일을 읽을 때 메타데이터 파일의 특정 형식을 적절한 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] 또는 CLR 형식에 자동으로 매핑합니다. 예를 들어 CLR에서 IVector\<T\> 인터페이스는 IList\<T\>에 매핑됩니다. 그러나 [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]에서 IVector\<T\> 인터페이스는 다른 형식에 매핑되지 않습니다.  
  
 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]의 IReference\<T\>는 .NET의 Nullable\<T\>에 매핑됩니다.  
  
## 참고 항목  
 [다른 언어와의 상호 운용](../cppcx/interoperating-with-other-languages-c-cx.md)