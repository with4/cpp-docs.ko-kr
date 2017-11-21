---
title: "정적 라이브러리 (C + + /cli CX) | Microsoft Docs"
ms.custom: 
ms.date: 02/03/2017
ms.prod: windows-client-threshold
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7faf53c8-fa21-42cc-8246-d32533ef9dfa
caps.latest.revision: "10"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 5f86d24c693cfcd5eecf8b37f0e4567c9c7af3a0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="static-libraries-ccx"></a>정적 라이브러리(C++/CX)
유니버설 Windows 플랫폼 앱에서 사용 되는 정적 라이브러리는 STL 형식 및 유니버설 Windows 플랫폼 앱 플랫폼에서 제외 되지 않은 Win32 Api에 대 한 호출을 비롯 한 ISO 표준 c + + 코드를 포함할 수 있습니다. 정적 라이브러리 Windows 런타임 구성 요소를 사용 하 고 특정 제한 사항이 있는 Windows 런타임 구성 요소를 만들 수 있습니다.  
  
## <a name="creating-static-libraries"></a>정적 라이브러리 만들기  
  
#### <a name="to-create-a-static-library-for-use-in-a-universal-windows-platform-app"></a>유니버설 Windows 플랫폼 앱에서 사용 하기 위해 정적 라이브러리를 만들려면  
  
1.  메뉴 모음에서 **파일** > **새로** > **프로젝트** > **빈 정적 라이브러리** 유니버설 windows 플랫폼 앱.  
  
2.  **솔루션 탐색기**에서 프로젝트의 바로 가기 메뉴를 열고 **속성**을 선택합니다. 에 **속성** 대화 상자의 **구성 속성** > **일반** 페이지에서 유니버설 Windows 플랫폼 앱 지원을 설정  **예**합니다.  
  
3.  에 **구성 속성** > **C/c + +** 페이지에서 설정 **사용** Windows 런타임 **확장** 를**예 (/ZW)**합니다.  
  
 컴파일러에서 오류 C3861 "식별자를 찾을 수 없습니다." 유니버설 Windows 플랫폼 앱에 대 한 제외 된 Win32 API를 호출 하는 경우 새 정적 라이브러리를 컴파일할 때 발생 참조에 Windows 런타임에서 지원 되는 대체 방법을 찾으려면 [Windows 스토어 앱의 Windows Api에 대 한 대안](http://msdn.microsoft.com/en-us/75568012-61e0-41cc-a4df-c698f54f21ec)합니다.  
  
 유니버설 Windows 플랫폼 지원 속성을로 설정 되도록 라이브러리 프로젝트의 속성 설정을 업데이트 해야 할 수는 유니버설 Windows 플랫폼 앱 솔루션에 c + + 정적 라이브러리 프로젝트를 추가 하는 경우 **예**합니다. 이 설정이 없으면 코드가 빌드되고 연결되지만 [!INCLUDE[win8_appstore_long](../cppcx/includes/win8-appstore-long-md.md)]용 응용 프로그램을 확인하려고 할 때 오류가 발생합니다. 정적 lib는 해당 lib를 사용하는 프로젝트와 동일한 컴파일러 설정을 사용하여 컴파일해야 합니다.  
  
 public `ref` 클래스, 공용 인터페이스 클래스 또는 공용 값 클래스를 만드는 정적 라이브러리를 사용하면 링커가 다음과 같은 경고를 발생시킵니다.  
  
> **LNK4264 경고:** Windows 런타임 형식을 작성할 때 것은 권장 되지 않는다고 Windows 런타임 메타 데이터를 포함 하는 정적 라이브러리와 연결할 참고를 정적 라이브러리로; /ZW로 컴파일된 개체 파일을 보관 합니다.  
  
 정적 라이브러리가 라이브러리 자체의 외부에 사용 되는 Windows 런타임 구성 요소를 생성 하지 않은 경우에 경고를 무시 해도 됩니다. 라이브러리에 정의된 구성 요소가 라이브러리에 사용되지 않는 경우 링커는 공용 메타 데이터에 형식 정보가 있는 경우에도 구현을 최적화할 수 있습니다. 즉, 정적 라이브러리의 공용 구성 요소는 컴파일되지만 런타임에 활성화되지 않습니다. 이러한 이유로 모든 Windows 런타임 구성 요소는 소비 대상으로 하는 다른 구성 요소나 앱에서 동적 연결 라이브러리 (DLL)에 구현 되어야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [스레딩 및 마샬링](../cppcx/threading-and-marshaling-c-cx.md)