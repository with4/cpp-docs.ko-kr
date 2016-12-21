---
title: "자동화 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "자동화 서버, 자동화 서버 정보"
  - "클라이언트, 자동화"
  - "프로그래밍 컨트롤[C++]"
  - "속성[MFC], 자동화"
  - "MFC[C++], COM 지원"
  - "OLE 자동화"
  - "자동화"
  - "서버[C++], 자동화"
  - "자동화 클라이언트"
  - "샘플 응용 프로그램[MFC], 자동화"
  - "메서드[MFC]"
  - "매개 변수 전달, 자동화"
  - "자동화 메서드"
  - "자동화, 매개 변수 전달"
  - "자동화 속성"
  - "MFC COM, 자동화"
  - "메서드[MFC], 자동화"
ms.assetid: 329117f0-c1aa-4680-a901-bfb71277dfba
caps.latest.revision: 13
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 자동화
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

자동화\(이전의 OLE 자동화\) 기술은 한 응용 프로그램에서 다른 응용 프로그램에 구현된 개체를 조작하거나 개체를 조작할 수 있도록 노출시키는 것을 가능하게 하는 기술입니다.  
  
 [자동화 서버](../mfc/automation-servers.md)는 COM 인터페이스를 통해 다른 응용 프로그램\([자동화 클라이언트](../mfc/automation-clients.md)\)에 기능을 노출하는 응용 프로그램\(COM 서버의 일종\)입니다. 자동화 서버에서 기능을 노출시키면 자동화 클라이언트는 개체에 직접 액세스하여 해당 개체에서 제공하는 서비스를 사용하는 방법으로 특정 기능을 자동화할 수 있습니다.  
  
 자동화 서버 및 클라이언트는 항상 `IDispatch`에서 파생되는 COM 인터페이스를 사용하며 자동화 형식이라고 하는 특정 데이터 형식을 사용 및 반환합니다. 자동화 인터페이스를 노출시킴으로써 다른 응용 프로그램에서 액세스할 수 있는 메서드 및 속성을 제공하는 개체는 모두 자동화할 수 있습니다. 자동화는 OLE 및 COM 개체 모두에 대해 사용할 수 있습니다. 자동화된 개체는 전역 개체 또는 원격 개체\(다른 컴퓨터에서 네트워크를 통해 액세스할 수 있는 개체\)이므로 다음과 같은 두 가지 범주로 나눌 수 있습니다.  
  
-   로컬 자동화  
  
-   [원격 자동화](../mfc/remote-automation.md)\(네트워크에서 분산 DCOM 또는 DCOM 사용\)  
  
 개체 노출은 응용 프로그램에서 다른 응용 프로그램에 유용한 기능을 제공할 때 편리한 기능입니다. 예를 들어, ActiveX 컨트롤은 자동화 서버의 일종이며 ActiveX 컨트롤을 사용하는 응용 프로그램은 해당 컨트롤의 자동화 클라이언트입니다.  
  
 또 다른 예로, 워드 프로세서에서는 해당 프로그램의 맞춤법 검사 기능을 다른 프로그램에 노출시킬 수 있습니다. 개체 노출을 통해 공급업체는 다른 응용 프로그램의 기존 기능을 사용하여 자사 응용 프로그램의 기능을 향상시킬 수 있습니다. 이런 자동화 방법으로 다시 사용하거나 캡슐화가 가능한 개체 지향 프로그래밍의 몇 가지 원칙을 응용 프로그램 수준에서 구현할 수 있습니다.  
  
 보다 중요한 것은 자동화 지원이 사용자 및 솔루션 공급자에게 제공된다는 것입니다. 자동화는 잘 정의된 공용 인터페이스를 통해 응용 프로그램 기능을 노출시킴으로써 다양한 응용 프로그램 고유의 매크로 언어 대신 Microsoft Visual Basic 같은 일반 프로그래밍 언어만으로 복잡한 솔루션을 빌드할 수 있게 합니다.  
  
 Microsoft Excel이나 Microsoft Visual C\+\+ 같은 대부분의 상업용 응용 프로그램에서는 사용자가 대부분의 응용 프로그램 기능을 자동화할 수 있습니다. 예를 들어 Visual C\+\+에서는 [VBScript](vtoriVBScript) 매크로를 만들어 빌드, 코드 편집 또는 디버깅 작업을 자동화할 수 있습니다.  
  
##  <a name="_core_passing_parameters_in_automation"></a> 자동화에서의 매개 변수 전달  
 자동화 메서드를 만드는 어려움 중 하나는 공통적이고 "안전한" 메커니즘을 통해 자동화 서버와 자동화 클라이언트 간에 데이터를 전달하는 것입니다. 자동화에서는 **VARIANT** 형식을 사용하여 데이터를 전달하며,**VARIANT** 형식은 태그가 지정된 공용 구조체입니다. 이 형식은 해당 값에 대한 데이터 멤버\(익명 C\+\+ 공용 구조체\)와 공용 구조체에 저장된 정보 형식을 나타내는 데이터 멤버를 가지고 있습니다.**VARIANT** 형식은 2바이트 및 4바이트 정수, 4바이트 및 8바이트 부동 소수점 수, 문자열, 부울 값 등의 여러 가지 표준 데이터 형식을 지원합니다. 또한, `HRESULT`\(OLE 오류 코드\), **CURRENCY**\(고정 소수점 숫자 형식\) 및 **DATE**\(절대 날짜 및 시간\) 형식을 지원하고 **IUnknown** 및 `IDispatch` 인터페이스에 대한 포인터도 지원합니다.  
  
 **VARIANT** 형식은 [COleVariant](../mfc/reference/colevariant-class.md) 클래스에 캡슐화되어 있습니다. 지원되는 **CURRENCY** 및 **DATE** 클래스는 [COleCurrency](../mfc/reference/colecurrency-class.md) 및 [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md) 클래스에 캡슐화되어 있습니다.  
  
## 자동화 샘플  
  
-   [AUTOCLIK](../top/visual-cpp-samples.md) 자동화 기술을 익히고 원격 자동화를 이해하도록 도와 줍니다.  
  
-   [ACDUAL](../top/visual-cpp-samples.md) 자동화 서버 응용 프로그램에 이중 인터페이스를 추가합니다.  
  
-   [CALCDRIV](../top/visual-cpp-samples.md) MFCCALC를 구동하는 자동화 클라이언트 응용 프로그램입니다.  
  
-   [INPROC](../top/visual-cpp-samples.md) In\-Process 자동화 서버 응용 프로그램의 예를 보여 줍니다.  
  
-   [IPDRIVE](../top/visual-cpp-samples.md) INPROC를 구동하는 자동화 클라이언트 응용 프로그램입니다.  
  
-   [MFCCALC](../top/visual-cpp-samples.md) 자동화 클라이언트 응용 프로그램의 예를 보여 줍니다.  
  
## 추가 정보  
  
-   [자동화 클라이언트](../mfc/automation-clients.md)  
  
-   [자동화 서버](../mfc/automation-servers.md)  
  
-   [원격 자동화](../mfc/remote-automation.md)  
  
-   [OLE](../mfc/ole-in-mfc.md)  
  
-   [액티드 기술](../mfc/mfc-com.md)  
  
## 원하는 작업을 선택하세요.  
  
-   [자동화 클래스 추가](../mfc/automation-servers.md)  
  
-   [형식 라이브러리 사용](../mfc/automation-clients-using-type-libraries.md)  
  
-   [자동화에서의 매개 변수 전달](#_core_automation_topics)  
  
-   [자동화 서버 액세스](../mfc/automation-servers.md)  
  
-   [C\+\+로 자동화 클라이언트 작성](../mfc/automation-clients.md)  
  
## 참고 항목  
 [MFC COM](../mfc/mfc-com.md)