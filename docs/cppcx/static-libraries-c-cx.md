---
title: "정적 라이브러리(C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "02/03/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7faf53c8-fa21-42cc-8246-d32533ef9dfa
caps.latest.revision: 10
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 10
---
# 정적 라이브러리(C++/CX)
[!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] 앱에서 사용되는 정적 라이브러리에는 STL 형식을 비롯한 ISO 표준 C\+\+ 코드와 [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] 앱 플랫폼에서 제외되지 않은 Win32 API에 대한 호출이 포함될 수 있습니다. 정적 라이브러리는 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 구성 요소를 사용하며, [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 구성 요소를 만들 수 있지만 일부 제한이 있습니다.  
  
## 정적 라이브러리 만들기  
  
#### [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] 응용 프로그램에서 사용할 정적 라이브러리 프로젝트를 만들려면  
  
1.  메뉴 모음에서 [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] 앱에 대해 **파일** \> **새로 만들기** \> **프로젝트** \> **빈 정적 라이브러리**를 선택합니다.  
  
2.  **솔루션 탐색기**에서 프로젝트의 바로 가기 메뉴를 열고 **속성**을 선택합니다.**속성** 대화 상자의 **구성 속성** \> **일반** 페이지에서 [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] 앱 지원을 **예**로 설정합니다.  
  
3.  **구성 속성** \> **C\/C\+\+** 페이지에서 **확장** [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]**사용**을 **예\(\/ZW\)**로 설정합니다.  
  
 새 정적 라이브러리를 컴파일할 때 [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] 앱에서 제외된 Win32 API를 호출하면 컴파일러에서 오류 C3861 “식별자를 찾을 수 없습니다.”가 발생합니다.[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]에 지원되는 다른 방법을 찾아보려면 [Alternatives to Windows APIs in Windows Store apps](http://msdn.microsoft.com/ko-kr/75568012-61e0-41cc-a4df-c698f54f21ec)을 참조하세요.  
  
 [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] 앱 솔루션에 C\+\+ 정적 라이브러리 프로젝트를 추가하는 경우 [!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] 지원 속성이 **예**로 설정되도록 라이브러리 프로젝트의 속성 설정을 업데이트해야 할 수 있습니다. 이 설정이 없으면 코드가 빌드되고 연결되지만 [!INCLUDE[win8_appstore_long](../cppcx/includes/win8-appstore-long-md.md)]용 응용 프로그램을 확인하려고 할 때 오류가 발생합니다. 정적 lib는 해당 lib를 사용하는 프로젝트와 동일한 컴파일러 설정을 사용하여 컴파일해야 합니다.  
  
 public `ref` 클래스, 공용 인터페이스 클래스 또는 공용 값 클래스를 만드는 정적 라이브러리를 사용하면 링커가 다음과 같은 경고를 발생시킵니다.  
  
> **warning LNK4264:** \/ZW로 컴파일된 개체 파일을 정적 라이브러리에 보관합니다. [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 형식을 작성할 때는 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 메타데이터를 포함하는 정적 라이브러리와 연결하지 않는 것이 좋습니다.  
  
 정적 라이브러리가 라이브러리 자체의 외부에서 사용되는 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 구성 요소를 생성하지 않는 경우에만 경고를 무시해도 됩니다. 라이브러리에 정의된 구성 요소가 라이브러리에 사용되지 않는 경우 링커는 공용 메타 데이터에 형식 정보가 있는 경우에도 구현을 최적화할 수 있습니다. 즉, 정적 라이브러리의 공용 구성 요소는 컴파일되지만 런타임에 활성화되지 않습니다. 따라서 다른 구성 요소나 앱에서 사용하도록 설계된 모든 [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 구성 요소는 DLL\(동적 연결 라이브러리\)에 구현되어야 합니다.  
  
## 참고 항목  
 [스레딩 및 마샬링](../cppcx/threading-and-marshaling-c-cx.md)