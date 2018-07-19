---
title: 인터넷의 비동기 모니커 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [MFC], asynchronous
- MFC, asynchronous monikers
- asynchronous monikers [MFC]
- Web applications [MFC], asynchronous
- downloading Internet resources and asynchronous monikers
- optimization [MFC], asynchronous downloading across Internet
- Internet [MFC], asynchronous downloading
ms.assetid: 418b0c64-0046-4dae-8118-c9c762b5822e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fb9828734985c25996e7e2d1a6f390a0b629d998
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343365"
---
# <a name="asynchronous-monikers-on-the-internet"></a>인터넷의 비동기 모니커
인터넷은 속도가 느린 네트워크 액세스로 인해 응용 프로그램 디자인 하기 위해 새로운 접근 방식이 필요합니다. 응용 프로그램 사용자 인터페이스를 정지 하지 않도록를 비동기적으로 네트워크 액세스를 수행 해야 합니다. MFC 클래스 [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) 파일을 다운로드 하는 것에 대 한 비동기 지원을 제공 합니다.  
  
 비동기 모니커 인터넷을 통해 비동기적으로 다운로드 하 고 비트맵와 같은 큰 개체 및 VRML 개체의 점진적 렌더링을 제공 하 여 COM 응용 프로그램을 확장할 수 있습니다. ActiveX 컨트롤 속성 또는 사용자 인터페이스의 응답을 차단 하지 않고 다운로드 하려면 인터넷에 있는 파일 비동기 모니커를 사용 합니다.  
  
## <a name="advantages-of-asynchronous-monikers"></a>비동기 모니커의 장점  
 비동기 모니커를 사용할 수 있습니다.  
  
-   차단 하지 않고 코드 및 파일을 다운로드 합니다.  
  
-   ActiveX 컨트롤의에서 속성을 차단 하지 않고 다운로드 합니다.  
  
-   다운로드 진행률에 대 한 알림을 받습니다.  
  
-   진행률 및 준비 상태 정보를 추적 합니다.  
  
-   진행률에 대 한 사용자에 게 상태 정보를 제공 합니다.  
  
-   언제 든 지 다운로드를 취소할 수 있습니다.  
  
## <a name="mfc-classes-for-asynchronous-monikers"></a>비동기 모니커 위한 MFC 클래스  
 [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md) 에서 파생 된 [CMonikerFile](../mfc/reference/cmonikerfile-class.md)를 차례로에서 파생 된 [COleStreamFile](../mfc/reference/colestreamfile-class.md)합니다. A `COleStreamFile` 개체에서 나타내는 데이터의 스트림을 있으며 `CMonikerFile` 개체에서 사용 하는 `IMoniker` 데이터를 가져오려면 및 `CAsyncMonikerFile` 개체가 비동기적으로 수행 합니다.  
  
 비동기 모니커는 주로 인터넷 사용 응용 프로그램 및 ActiveX 컨트롤에서 파일을 전송 하는 동안 응답성이 뛰어난 사용자 인터페이스를 제공 하는 데 사용 됩니다. 사용 하는 것이 가장 대표적인 예 [CDataPathProperty](../mfc/reference/cdatapathproperty-class.md) 에 ActiveX 컨트롤에 대 한 비동기 속성을 제공 합니다.  
  
## <a name="mfc-classes-for-data-paths-in-activex-controls"></a>ActiveX 컨트롤의 데이터 경로 대 한 MFC 클래스  
 MFC 클래스 `CDataPathProperty` 및 [CCachedDataPathProperty](../mfc/reference/ccacheddatapathproperty-class.md) 비동기적으로 로드 될 수 있는 ActiveX 컨트롤 속성을 구현 합니다. 비동기 속성이 동기 시작 후 로드 됩니다. 비동기 ActiveX 컨트롤에는 반복적으로 긴 속성 교환 과정 동안 새 데이터의 가용성을 나타내기 위해 콜백을 호출 합니다.  
  
 `CDataPathProperty`는 `CAsyncMonikerFile`에서 파생됩니다. `CCachedDataPathProperty`는 `CDataPathProperty`에서 파생됩니다. ActiveX 컨트롤의 비동기 속성을 구현 하려면에서 클래스를 파생 `CDataPathProperty` 또는 `CCachedDataPathProperty`, 재정의 및 [OnDataAvailable](../mfc/reference/casyncmonikerfile-class.md#ondataavailable) 및 기타 알림을 수신 하려면.  
  
#### <a name="to-download-a-file-using-asynchronous-monikers"></a>비동기 모니커를 사용 하 여 파일을 다운로드 하려면  
  
1.  파생 된 클래스를 선언 [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md)합니다.  
  
2.  재정의 [OnDataAvailable](../mfc/reference/casyncmonikerfile-class.md#ondataavailable) 데이터를 표시 합니다.  
  
3.  다른 멤버 함수를 포함 하 여 재정의 [OnProgress](../mfc/reference/casyncmonikerfile-class.md#onprogress), [OnStartBinding](../mfc/reference/casyncmonikerfile-class.md#onstartbinding), 및 [OnStopBinding](../mfc/reference/casyncmonikerfile-class.md#onstopbinding)합니다.  
  
4.  이 클래스의 인스턴스를 선언 하 고 사용 하 여 Url을 엽니다.  
  
 ActiveX 컨트롤에서 비동기적으로 다운로드에 대 한 정보를 참조 하십시오. [인터넷의 ActiveX 컨트롤](../mfc/activex-controls-on-the-internet.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [MFC 인터넷 프로그래밍 작업](../mfc/mfc-internet-programming-tasks.md)   
 [MFC 인터넷 프로그래밍 기본 사항](../mfc/mfc-internet-programming-basics.md)

