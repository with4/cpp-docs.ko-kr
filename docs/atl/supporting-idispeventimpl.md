---
title: "IDispEventImpl 지원 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: IDispEventImpl
dev_langs: C++
helpviewer_keywords:
- event sink maps, declaring
- IDispEventImpl class, advising and unadvising
- SINK_ENTRY macro
- type libraries, importing
- ATL, IDispEventImpl support in COM objects
- BEGIN_SINK_MAP macro
- IDispEventImpl class, declaring
ms.assetid: b957f930-6a5b-4598-8e4d-8027759957e7
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8bf10a68ae15743a637df2dee52bee83c3dfcbe0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="supporting-idispeventimpl"></a>IDispEventImpl 지원
템플릿 클래스 [IDispEventImpl](../atl/reference/idispeventimpl-class.md) 는 연결 지점 싱크에 ATL 클래스에 대 한 지원을 제공 하는 데 사용할 수 있습니다. 연결 지점 싱크 클래스를를 COM 개체 외부에서 발생 하는 이벤트를 처리할 수 있습니다. 이러한 연결 지점 싱크는 클래스에서 제공 하는 이벤트 싱크 맵이 매핑됩니다.  
  
 클래스에 대 한 연결 지점 싱크를 제대로 구현 하려면 다음 단계를 완료 해야 합니다.  
  
-   각 외부 개체에 대 한 형식 라이브러리 가져오기  
  
-   선언 된 `IDispEventImpl` 인터페이스  
  
-   이벤트 싱크 맵 선언  
  
-   싱 및 unadvise 연결 지점  
  
 연결 지점 싱크를 구현 하는 단계는 모두 헤더 파일 (.h) 클래스를 수정 하 여 수행 됩니다.  
  
## <a name="importing-the-type-libraries"></a>형식 라이브러리 가져오기  
 각 개체에 대해 외부 이벤트를 처리, 형식 라이브러리를 가져와야 합니다. 이 단계는 처리 될 수 있는 이벤트를 정의 하 고 이벤트 싱크 맵 선언할 때 사용 되는 정보를 제공 합니다. [#import](../preprocessor/hash-import-directive-cpp.md) 지시문이를 위해 사용할 수 있습니다. 필요한 추가 `#import` 지시문 줄을 각 디스패치 인터페이스 클래스의 헤더 파일 (.h)를 지원 합니다.  
  
 다음 예에서는 외부 COM 서버의 형식 라이브러리를 가져옵니다 (`MSCAL.Calendar.7`):  
  
 [!code-cpp[NVC_ATL_Windowing#141](../atl/codesnippet/cpp/supporting-idispeventimpl_1.h)]  
  
> [!NOTE]
>  별도 있어야 `#import` 지원할 각 외부 형식 라이브러리에 대 한 문입니다.  
  
## <a name="declaring-the-idispeventimpl-interfaces"></a>IDispEventImpl 인터페이스 선언  
 별도 선언 해야 하는 각 디스패치 인터페이스의 형식 라이브러리를 가져온 했으므로 `IDispEventImpl` 각 외부 디스패치 인터페이스에 대 한 인터페이스입니다. 클래스의 선언을 추가 하 여 수정 된 `IDispEventImpl` 인터페이스 선언을 각 외부 개체에 대 한 합니다. 매개 변수에 대 한 자세한 내용은 참조 하십시오. [IDispEventImpl](../atl/reference/idispeventimpl-class.md)합니다.  
  
 다음 코드에 대 한 두 개의 연결 지점 싱크에 선언 된 `DCalendarEvents` 클래스에 의해 구현 된 COM 개체에 대 한 인터페이스 `CMyCompositCtrl2`:  
  
 [!code-cpp[NVC_ATL_Windowing#142](../atl/codesnippet/cpp/supporting-idispeventimpl_2.h)]  
  
## <a name="declaring-an-event-sink-map"></a>이벤트 싱크 맵 선언  
 적절 한 함수에 의해 처리 되는 이벤트 알림에 대 한 순서로 클래스 올바른 처리기에 각 이벤트를 라우팅해야 합니다. 이 이벤트 싱크 맵을 선언 하 여 달성 됩니다.  
  
 ATL는 여러 가지 매크로가 [BEGIN_SINK_MAP](reference/composite-control-macros.md#begin_sink_map), [END_SINK_MAP](reference/composite-control-macros.md#end_sink_map), 및 [SINK_ENTRY_EX](reference/composite-control-macros.md#sink_entry_ex),이 매핑은 더 쉽게 하 합니다. 표준 형식은 다음과 같습니다.  
  
 `BEGIN_SINK_MAP(comClass)`  
  
 `SINK_ENTRY_EX(id, iid, dispid, func)`  
  
 `. . . //additional external event entries`  
  
 `END_SINK_MAP()`  
  
 다음 예제에서는 두 명의 이벤트 처리기와 이벤트 싱크 맵이라고를 선언합니다.  
  
 [!code-cpp[NVC_ATL_Windowing#136](../atl/codesnippet/cpp/supporting-idispeventimpl_3.h)]  
  
 구현은 거의 완료 되었습니다. 외부 인터페이스의 바이 싱 및 관련 된 마지막 단계입니다.  
  
## <a name="advising-and-unadvising-the-idispeventimpl-interfaces"></a>싱 및 바이 IDispEventImpl 인터페이스  
 마지막 단계는 적절 한 시간에는 advise (하거나 unadvise) 모든 연결 지점 하는 메서드를 구현 하는 것입니다. 이 확인 하 라는 후 외부 클라이언트와 개체 간의 통신을 수행할 수 있습니다. 개체를 표시 하기 전에 개체가 지 원하는 외부 디스패치 인터페이스 각 송신 인터페이스에 대 한 쿼리 됩니다. 연결이 설정 되 고 송신 인터페이스에 대 한 참조는 개체에서 이벤트를 처리 하는 데 사용 됩니다. 이 절차는 라고도 "조언 합니다."  
  
 개체는 외부 인터페이스를 통해 완료 되 면 송신 인터페이스가 사람과 알림을 받는 클래스에서 더 이상 사용 됩니다. 이 프로세스 라고 "바이."  
  
 COM 개체의 고유 특성상이 절차의 세부 데이터와 구현 간의 실행 하 고 달라 집니다. 이러한 세부 정보는이 항목의 범위를 벗어나는 및 다루지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [ATL COM 개체 기본 사항](../atl/fundamentals-of-atl-com-objects.md)

