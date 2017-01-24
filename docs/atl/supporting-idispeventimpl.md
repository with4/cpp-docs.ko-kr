---
title: "Supporting IDispEventImpl | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDispEventImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, IDispEventImpl support in COM objects"
  - "BEGIN_SINK_MAP macro"
  - "event sink maps, 선언"
  - "IDispEventImpl class, advising and unadvising"
  - "IDispEventImpl class, 선언"
  - "SINK_ENTRY macro"
  - "형식 라이브러리, 가져오기"
ms.assetid: b957f930-6a5b-4598-8e4d-8027759957e7
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Supporting IDispEventImpl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

템플릿 클래스  [IDispEventImpl](../atl/reference/idispeventimpl-class.md) ATL 클래스에 연결 지점 싱크를 지원 하기 위해 사용할 수 있습니다.  연결 지점 싱크 클래스를 외부 COM 개체에서 발생 하는 이벤트를 처리할 수 있습니다.  이러한 연결 지점 싱크는 클래스가 제공 하는 이벤트 싱크 맵을 함께 매핑됩니다.  
  
 클래스에는 연결 지점 싱크를 제대로 구현 하려면 다음 단계를 완료 합니다.  
  
-   각 외부 개체에 대 한 형식 라이브러리 가져오기  
  
-   선언 된 `IDispEventImpl` 인터페이스  
  
-   하는 이벤트 싱크 맵을 선언 합니다.  
  
-   싱 및 연결점 싱  
  
 연결 지점 싱크 구현에 관련 된 단계를 통해 모든 헤더 파일 \(.h\)의 클래스를 수정 하 여 수행할 수 있습니다.  
  
## 형식 라이브러리 가져오기  
 이벤트를 처리 하려는 각 외부 개체에 대 한 형식 라이브러리를 가져와야 합니다.  이 단계는 처리할 수 있는 이벤트를 정의 및 이벤트 싱크 맵을 선언할 때 사용 되는 정보를 제공 합니다.  [\# Import](../preprocessor/hash-import-directive-cpp.md) 지시문을 사용 하 여이 작업을 수행 합니다.  필요한 추가 `#import` 지시문 줄 각각의 디스패치 인터페이스 클래스 헤더 파일 \(.h\)에 지원 됩니다.  
  
 다음 예제에서는 외부 COM 서버의 형식 라이브러리 가져오기 \(`MSCAL.Calendar.7`\).  
  
 [!code-cpp[NVC_ATL_Windowing#141](../atl/codesnippet/CPP/supporting-idispeventimpl_1.h)]  
  
> [!NOTE]
>  별도 있어야 `#import` 를 지원할 각 외부 형식 라이브러리에 대 한 문의.  
  
## IDispEventImpl 인터페이스 선언  
 각 디스패치 인터페이스의 형식 라이브러리를 가져온 했으므로 별도 선언 해야 `IDispEventImpl` 각 외부 디스패치 인터페이스에 대해 인터페이스.  클래스 선언을 추가 하 여 수정 된 `IDispEventImpl` 인터페이스를 선언 하는 각 외부 개체에 대 한.  매개 변수에 대 한 자세한 내용은 참조 하십시오.  [IDispEventImpl](../atl/reference/idispeventimpl-class.md).  
  
 에 대 한 두 연결 지점 싱크를 선언 하는 다음 코드는 `DCalendarEvents` 인터페이스 클래스에 의해 구현 되는 COM 개체에 대 한 `CMyCompositCtrl2`.  
  
 [!code-cpp[NVC_ATL_Windowing#142](../atl/codesnippet/CPP/supporting-idispeventimpl_2.h)]  
  
## 하는 이벤트 싱크 맵을 선언합니다.  
 적절 한 함수에 의해 처리 되는 이벤트 알림을 순서로 클래스 각 이벤트를 올바른 처리기로 경로 설정 해야 합니다.  이 이벤트 싱크 맵을 선언 하 여 수행할 수 있습니다.  
  
 ATL 여러 매크로 제공 합니다.  [BEGIN\_SINK\_MAP](../Topic/BEGIN_SINK_MAP.md),  [END\_SINK\_MAP](../Topic/END_SINK_MAP.md), 및  [SINK\_ENTRY\_EX](../Topic/SINK_ENTRY.md), 하이 매핑을 쉽게.  표준 형식은 다음과 같습니다.  
  
 `BEGIN_SINK_MAP(comClass)`  
  
 `SINK_ENTRY_EX(id, iid, dispid, func)`  
  
 `.  .  .  //additional external event entries`  
  
 `END_SINK_MAP()`  
  
 다음 예제에서는 두 명의 이벤트 처리기에는 이벤트 싱크 맵을 선언합니다.  
  
 [!code-cpp[NVC_ATL_Windowing#136](../atl/codesnippet/CPP/supporting-idispeventimpl_3.h)]  
  
 구현이 거의 완료 되었습니다.  마지막 단계는 싱 및 외부 인터페이스의 바이 관련이 있습니다.  
  
## 싱 및 바이 IDispEventImpl 인터페이스  
 최종 단계 적당 한 시기에 권고 \(싱 모든 연결점 이나 됩니다\) 메서드를 구현 하는 것입니다.  이 싱 외부 클라이언트와 개체 사이 통신을 수행 하기 전에 수행 되어야 합니다.  개체를 표시 하기 전에 해당 개체에서 지 원하는 각 외부 디스패치 인터페이스에 대 한 나가는 인터페이스 쿼리 됩니다.  연결이 설정 되 고 나가는 인터페이스에 대 한 참조 개체에서 이벤트를 처리 하는.  이 절차를 "라는 이름으로." 라고  
  
 개체를 외부 인터페이스로 완료 되 면 송신 인터페이스는 클래스에 의해 더 이상 사용 되지 알려야 합니다.  이 프로세스를 "바이로." 라고  
  
 COM 개체의 고유한 특성으로 인해이 절차 세부 및 실행 구현 간의 다릅니다.  이러한 세부 정보는이 항목에서 다루지 않습니다 및 해결 하지.  
  
## 참고 항목  
 [Fundamentals of ATL COM Objects](../atl/fundamentals-of-atl-com-objects.md)