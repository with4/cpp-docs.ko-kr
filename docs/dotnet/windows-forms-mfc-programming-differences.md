---
title: "Windows Forms MFC 프로그래밍의 차이점 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC [C++], Windows Forms support
- Windows Forms [C++], compared to MFC
ms.assetid: f3bfcf45-cfd4-45a4-8cde-5f4dbb18ee51
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 696e7684eb91abbf41e3f7a2e1df20b6fa7e5c17
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="windows-formsmfc-programming-differences"></a>Windows Forms/MFC 프로그래밍의 차이점
항목에서는 [MFC의 Windows Form 사용자 정의 컨트롤을 사용 하 여](../dotnet/using-a-windows-form-user-control-in-mfc.md) Windows Forms에 대 한 MFC 지원을 설명 합니다. .NET Framework 또는 MFC 프로그래밍에 익숙한 경우이 항목 프로그래밍 방식 둘 사이의 차이점에 대 한 배경 정보를 제공 합니다.  
  
 Windows Forms는.NET Framework에서 Microsoft Windows 응용 프로그램을 만들기 위한입니다. 이 프레임 워크는 다양 한 Windows 기반 응용 프로그램을 개발할 수 있게 하는 클래스의 최신, 개체 지향, 확장 가능한 집합을 제공 합니다. Windows Forms 하면 다양 한 데이터 원본에 액세스 하 고 데이터 표시 및 Windows Forms 컨트롤을 사용 하 여 데이터 편집 기능을 제공할 수 있는 리치 클라이언트 응용 프로그램을 만들 수 있습니다.  
  
 그러나 MFC에 익숙하다면, 특정 종류의 Windows Forms에서 아직 명시적으로 지원 되지 않는 응용 프로그램을 만드는 데 있습니다를 사용할 수 있습니다. Windows Forms 응용 프로그램 MFC 대화 상자 응용 프로그램에 동일합니다. 그러나 제공 하지 않습니다 직접 단일 문서 인터페이스 (SDI) 다중 문서 인터페이스 mdi (다중)에 대 한 OLE 문서 서버/컨테이너, ActiveX 문서, 문서/뷰 지원을 같은 다른 MFC 응용 프로그램 종류를 지원 하도록 인프라 및 여러 최상위 인터페이스 (MTI)입니다. 이러한 응용 프로그램을 만드는 고유한 논리를 작성할 수 있습니다.  
  
 Windows Forms 응용 프로그램에 대 한 자세한 내용은 참조 [Windows Forms 소개](/dotnet/framework/winforms/windows-forms-overview)합니다.  
  
 MFC와 함께 사용 되는 Windows Forms를 보여 주는 샘플 응용 프로그램을 참조 하십시오. [MFC 및 Windows Forms 통합](http://www.microsoft.com/downloads/details.aspx?FamilyID=987021bc-e575-4fe3-baa9-15aa50b0f599&displaylang=en)합니다.  
  
 MFC 뷰로 또는 문서 आ स ा 명령 라우팅 기능에는 Windows Forms에서 해당가지고 있습니다.  
  
-   셸 통합  
  
     MFC에 동적 데이터 교환 (DDE) 명령 및 문서를 마우스 오른쪽 단추로 클릭 하 고 열기으로 이러한 동사를 선택, 편집 또는 인쇄 하는 경우 셸에서 사용 하는 명령줄 인수를 처리 합니다. Windows Forms 셸 통합 되지 않으므로 개이고 셸 동사에 응답 하지 않습니다.  
  
-   문서 템플릿  
  
     Mfc에서 문서 서식 파일을 연 문서 프레임 창 (MDI, SDI 또는 MTI 모드에서)에 포함 되어 있는 뷰를 연결 합니다. Windows Forms과 관련 문서 서식 파일에 있습니다.  
  
-   문서  
  
     MFC 문서 파일 유형에 등록 하 고 셸에서 문서를 열 때 문서 형식을 처리 합니다. Windows Forms에는 문서 지원 되지 않습니다.  
  
-   문서 상태  
  
     MFC의 문서에 대 한 변경 상태를 유지 관리합니다. 따라서 응용 프로그램을 종료, 응용 프로그램을 포함 하는 마지막 보기를 닫거나 Windows에서 종료, MFC 문서를 저장할 것인지 묻습니다. Windows Forms에는 해당 하는 지원 되지 않습니다.  
  
-   명령  
  
     MFC 개념 명령 중에 있습니다. 메뉴 모음, 도구 모음과 상황에 맞는 메뉴 모두 동일한 명령 예를 들어, 잘라내기 및 복사를 호출할 수 있습니다. Windows Forms 명령을 완전히 바인딩된 이벤트를 특정 UI 요소 (예: 메뉴 항목); 있습니다. 따라서 명령 이벤트를 모두 명시적으로 연결 해야 할 수도 있습니다. Windows Forms에서 단일 처리기로 여러 이벤트를 처리할 수 있습니다. 자세한 내용은 참조 [Windows Forms에서 단일 이벤트 처리기에 여러 이벤트 연결](/dotnet/framework/winforms/how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms)합니다.  
  
-   명령 라우팅  
  
     MFC 명령 라우팅 활성 뷰 또는 문서 명령 처리할 수 있습니다. 동일한 명령에는 종종 다른 보기에 대 한 서로 다른 의미로 있기 때문에 (예를 들어 복사본에서에서 다르게 작동 하는 그래픽 편집기에서 텍스트 편집 보기 보다), 명령이 현재 보기에서 처리 해야 합니다. 에 대 한 각 보기 유형에 별도 처리기를 사용할 수 없습니다 Windows Forms 메뉴와 도구 모음 현재 보기의 기본적인 이해 하지 못합니다를 가지기 때문에 프로그램 **MenuItem.Click** 추가 내부 코드를 작성 하지 않고도 이벤트입니다.  
  
-   명령 업데이트 메커니즘  
  
     MFC에는 명령 메커니즘을 업데이트 합니다. 따라서 활성 뷰 또는 문서는 UI 요소 (예: 하거나 설정 하 고, 메뉴 항목이 나 도구 단추를 사용 하지 않도록 설정 하 고, 상태 확인)의 상태를 담당 합니다. Windows Forms에 명령 업데이트 메커니즘의 해당 키 없음.  
  
## <a name="see-also"></a>참고 항목  
 [MFC의 Windows Form 사용자 정의 컨트롤을 사용 하 여](../dotnet/using-a-windows-form-user-control-in-mfc.md)   
 [Windows Forms 연습](http://msdn.microsoft.com/en-us/fd44d13d-4733-416f-aefc-32592e59e5d9)