---
title: "MFC 매크로 및 전역 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Afx 명명 규칙"
  - "전역 함수"
  - "전역 함수, MFC"
  - "전역 변수, MFC"
  - "매크로"
  - "매크로, MFC"
  - "MFC, 전역 함수 및 변수"
  - "MFC, 매크로"
ms.assetid: add4e33f-0e62-4d27-be14-896cb8675d22
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# MFC 매크로 및 전역
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Microsoft Foundation 클래스 라이브러리는 두 개의 주요 부분으로 나눌 수 있습니다: \(1\) MFC 클래스 및 \(2\) 매크로 및 전역.  함수나 변수는 클래스의 멤버가 아닐경우, 전역 함수 또는 변수입니다.  
  
 MFC 라이브러리와 액티브 템플릿 라이브러리 \(ATL\)는 문자열 변환 매크로를 공유합니다.  자세한 내용은 ATL 설명서에서 [String Conversion Macros](../../atl/reference/string-conversion-macros.md)를 참조하십시오.  
  
 MFC 매크로 및 전역은 다음 범주의 기능을 제공합니다.  
  
## 일반 MFC  
  
-   [데이터 형식](../../mfc/reference/data-types-mfc.md)  
  
-   [MFC 클래스 개체의 형식 캐스팅](../../mfc/reference/type-casting-of-mfc-class-objects.md)  
  
-   [런타임 개체 모델 서비스](../../mfc/reference/run-time-object-model-services.md)  
  
-   [진단 서비스](../../mfc/reference/diagnostic-services.md)  
  
-   [예외 처리](../../mfc/reference/exception-processing.md)  
  
-   [CString 서식 지정 및 메시지 상자 표시](../../mfc/reference/cstring-formatting-and-message-box-display.md)  
  
-   [메시지 맵](../../mfc/reference/message-map-macros-mfc.md)  
  
-   [응용 프로그램 정보 및 관리](../../mfc/reference/application-information-and-management.md)  
  
-   [표준 명령 및 창 ID](../../mfc/reference/standard-command-and-window-ids.md)  
  
-   [컬렉션 클래스 도우미](../../mfc/reference/collection-class-helpers.md)  
  
-   [회색 및 디더링된 비트맵 함수](../../mfc/reference/gray-and-dithered-bitmap-functions.md)  
  
-   [표준 대화 상자 데이터 교환 루틴\(DDX\)](../../mfc/reference/standard-dialog-data-exchange-routines.md)  
  
-   [표준 대화 상자 데이터 유효성 검사\(DDV\) 루틴](../../mfc/reference/standard-dialog-data-validation-routines.md)  
  
-   [AFX 메시지](../../mfc/reference/afx-messages.md)  
  
-   [ToolBar 컨트롤 스타일](../../mfc/reference/toolbar-control-styles.md)  
  
-   [CMFCImagePaintArea::IMAGE\_EDIT\_MODE 열거형](../../mfc/reference/cmfcimagepaintarea-image-edit-mode-enumeration.md)  
  
## 데이터베이스  
  
-   MFC ODBC 클래스에 대한 [레코드 필드 교환\(RFX\) 함수](../../mfc/reference/record-field-exchange-functions.md) 및  [대량 레코드 필드 교환\(bulk RFX\) 함수](../../mfc/reference/record-field-exchange-functions.md).  
  
-   MFC DAO 클래스에 대한 [레코드 필드 교환 \(DFX\) 함수](../../mfc/reference/record-field-exchange-functions.md).  
  
-   [CRecordView 및 CDaoRecordView에 대한 대화 상자 데이터 교환 \(DDX\) 함수](../../mfc/reference/dialog-data-exchange-functions-for-crecordview-and-cdaorecordview.md) \(MFC ODBC와 DAO 클래스\)  
  
-   [OLE 컨트롤에 대한 대화상자 데이터 교환\(DDX\) 함수](../../mfc/reference/dialog-data-exchange-functions-for-ole-controls.md)  
  
-   [개방형 데이터베이스 연결 \(ODBC\) API 함수를 직접 호출하는 데 도움이 되는 매크로 및 전역 변수.](../../mfc/reference/database-macros-and-globals.md)  
  
-   [DAO 데이터베이스 엔진 초기화 및 종료](../../mfc/reference/dao-database-engine-initialization-and-termination.md)  
  
## Internet  
  
-   [인터넷 URL 전역 구문 분석](../../mfc/reference/internet-url-parsing-globals.md)  
  
## DHTML \/ DHTML 이벤트 맵입니다.  
  
-   [DHTML 대화 상자 데이터 교환 \(DDX\) 도우미 매크로](../../mfc/reference/ddx-dhtml-helper-macros.md)  
  
-   [DHTML 이벤트 맵](../../mfc/reference/dhtml-event-maps.md)  
  
## OLE  
  
-   [OLE 초기화](../../mfc/reference/ole-initialization.md)  
  
-   [응용 프로그램 컨트롤](../../mfc/reference/application-control.md)  
  
-   [디스패치 맵](../../mfc/reference/dispatch-maps.md)  
  
 또한, MFC는 MFC 4.0으로 개발된 OLE 컨테이너를 사용할 수 있는 [AfxEnableControlContainer](../Topic/AfxEnableControlContainer.md)라는 함수를 제공하여 완벽하게 지원합니다.  
  
## OLE 컨트롤  
  
-   [가변 매개 변수 형식 상수](../../mfc/reference/variant-parameter-type-constants.md)  
  
-   [형식 라이브러리 액세스](../../mfc/reference/type-library-access.md)  
  
-   [속성 페이지](../../mfc/reference/property-pages-mfc.md)  
  
-   [이벤트 맵](../../mfc/reference/event-maps.md)  
  
-   [이벤트 싱크 맵](../../mfc/reference/event-sink-maps.md)  
  
-   [연결 맵](../../mfc/reference/connection-maps.md)  
  
-   [OLE 컨트롤 등록](../../mfc/reference/registering-ole-controls.md)  
  
-   [클래스 팩토리 및 라이선스](../../mfc/reference/class-factories-and-licensing.md)  
  
-   [OLE 컨트롤의 지속성](../../mfc/reference/persistence-of-ole-controls.md)  
  
 이 섹션의 첫 번째 부분은 간략하게 이전 범주 각각에 대해 설명하고, 기능에 대한 간략한 설명과 함께 범주의 전역 변수 및 매크로를 나열합니다.  다음은 MFC 라이브러리의 전역 함수, 전역 변수 및 매크로를 설명합니다.  
  
> [!NOTE]
>  많은 전역 함수가 "Afx" 접두사로 시작 하지만 일부 \-예를 들어, 대화 상자 데이터 교환 \(DDX\) 함수 및 많은 데이터베이스 기능\-는 이 규칙을 따르지 않습니다.  모든 전역 변수는 "afx" 접두사로 시작합니다.  특정 접두사를 사용하여 매크로 실행할 수 없습니다. 그러나 그것들은 대문자로 기록됩니다.  
  
## 참고 항목  
 [클래스 개요](../../mfc/class-library-overview.md)