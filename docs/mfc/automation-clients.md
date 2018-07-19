---
title: 자동화 클라이언트 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- clients, Automation
- Automation clients
- type libraries, Automation clients
- clients
ms.assetid: 84e34a79-06f6-4752-a33b-ae0ede1d8ecf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a29b11028df84a7e5e67adb7588386f77adcff06
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929041"
---
# <a name="automation-clients"></a>자동화 클라이언트
자동화를 다른 응용 프로그램에서 구현 된 개체를 조작 하거나 조작할 수 있도록 개체를 노출 시키는 응용 프로그램에 대 한 수 있게 합니다. 자동화 클라이언트는 다른 응용 프로그램에 속한 노출 된 개체를 조작할 수 있는 응용 프로그램. 개체를 표시 하는 응용 프로그램 자동화 서버를 라고 합니다. 클라이언트는 해당 개체의 속성 및 함수에 액세스 하 여 서버 응용 프로그램의 개체를 조작 합니다.  
  
### <a name="types-of-automation-clients"></a>종류의 자동화 클라이언트  
 자동화 클라이언트는 다음과 같은 두 종류가 있습니다.  
  
-   런타임에 동적으로 () 위한 속성 및 서버 작업에 대 한 정보를 수집 하는 클라이언트입니다.  
  
-   속성 및 서버 작업을 지정 하는 정적 정보 (컴파일 시 제공)를 소유 하는 클라이언트입니다.  
  
 첫 번째 종류의 클라이언트 OLE 시스템을 쿼리하여 서버의 메서드 및 속성에 대 한 정보를 획득 `IDispatch` 메커니즘입니다. 동적 클라이언트에 대해 사용할 적합 하지만 `IDispatch` 에 인식 되어야 영향 개체 컴파일 시간 정적 클라이언트에 사용 하기 어렵습니다. Microsoft Foundation 클래스를 제공 하는 정적 바인딩된 클라이언트를는 [COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md) 클래스입니다.  
  
 정적 바인딩된 클라이언트는 클라이언트 응용 프로그램 정적으로 링크 하는 프록시 클래스를 사용 합니다. 이 클래스는 서버 응용 프로그램의 속성 및 작업의 형식이 안전한 c + + 캡슐화를 제공합니다.  
  
 클래스 `COleDispatchDriver` 자동화의 클라이언트 쪽에 대 한 기본 지원을 제공 합니다. 사용 하 여 **새 항목 추가** 에서 파생 된 클래스를 만들면 대화 상자, `COleDispatchDriver`합니다.  
  
 그런 다음 속성 및 서버 응용 프로그램의 개체의 함수를 설명 하는 형식 라이브러리 파일을 지정 합니다. 항목 추가 대화 상자가이 파일을 읽고 만듭니다는 `COleDispatchDriver`-응용 프로그램 개체에 액세스 하려면 서버 응용 프로그램의 c + +의 형식이 안전한 방식으로 호출할 수 있는 멤버 함수를 사용 하 여 클래스를 파생 합니다. 추가 기능에서 상속 되며, `COleDispatchDriver` 적절 한 자동화 서버를 호출 하는 과정이 간단해 집니다.  
  
### <a name="handling-events-in-automation-clients"></a>자동화 클라이언트의 이벤트 처리  
 자동화 클라이언트에서 이벤트를 처리 하려면 싱크 인터페이스를 추가 해야 합니다. MFC는 ActiveX 컨트롤에 대 한 싱크 인터페이스를 추가 하지만 다른 COM 서버에 대 한 지원 하지 않습니다 마법사 지원을 제공 합니다. COM 서버에서 설명 하는 소스 인터페이스에 대 한 MFC 클라이언트에서 싱크 인터페이스를 추가 하는 방법에 대 한 자세한 내용은 방법을 참조 하십시오.: (KB 181845) MFC-Based COM 클라이언트의 싱크 인터페이스에서 만듭니다 [ http://support.microsoft.com/default.aspxscid=kb; en-us; 181845](http://support.microsoft.com/default.aspxscid=kb;en-us;181845)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [형식 라이브러리를 사용 하는 자동화 클라이언트:](../mfc/automation-clients-using-type-libraries.md)   
 [자동화](../mfc/automation.md)   
 [MFC 응용 프로그램 마법사](../mfc/reference/mfc-application-wizard.md)

