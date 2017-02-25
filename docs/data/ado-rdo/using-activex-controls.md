---
title: "ActiveX 컨트롤 사용 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX 컨트롤[C++], ActiveX 컨트롤 정보"
  - "컨트롤[C++], ActiveX"
ms.assetid: 33442173-205d-492f-82c8-9a8105358ec6
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# ActiveX 컨트롤 사용
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 단원의 항목에서는 ActiveX 컨트롤 사용에 대한 개요를 설명합니다.  
  
 ActiveX 컨트롤은 지속성, 연결 지점 및 호스팅과 관련된 표준 인터페이스를 지원하는 COM 구성 요소입니다.  이러한 표준 인터페이스는 컨트롤 컨테이너에서 컨트롤을 호스팅할 수 있는 프로토콜을 정의하고 메시지를 교환하고 이벤트를 처리합니다.  
  
 ActiveX 컨트롤은 COM 서버로서 다음과 같은 요소를 포함합니다.  
  
|용어|설명|  
|--------|--------|  
|속성|컨트롤에는 내부 상태를 나타내는 멤버 변수가 있으며 **Get** 및 `Set` 접근자 함수로 구현됩니다.  **Get** 함수는 .idl 파일에서 propget 태그가 있는 각 접근자 메서드에 대해 생성됩니다.  `Set` 함수는 propput이나 propputref IDL 태그가 있는 각 접근자 메서드에 대해 생성됩니다.<br /><br /> 접근자 함수를 정의하는 방법을 확인하려면 [래퍼 클래스](../../data/ado-rdo/wrapper-classes.md)나 [OLE\/COM 개체 뷰어](../../data/ado-rdo/using-the-ole-com-object-viewer.md)를 사용하십시오.|  
|메서드|컨트롤의 동작은 컨트롤의 공용 메서드에 의해 정의됩니다.  래퍼 클래스를 사용하면 컨트롤의 메서드에 액세스할 수 있습니다.<br /><br /> 래퍼 클래스를 사용하지 않을 경우\(기본값\) 인터페이스에 대한 포인터를 가져와 컨트롤의 메서드에 액세스합니다.<br /><br /> 공용 메서드의 예로는 ADO 데이터 컨트롤의 **Refresh** 메서드가 있으며 이 메서드는 검색된 행 집합을 업데이트합니다.|  
|이벤트|컨트롤은 이벤트를 생성하여 어떤 일이 발생했음을 호스트에 알릴 수 있습니다.  Button 컨트롤에 대한 `OnClick` 이벤트를 예로 들 수 있습니다.  단추를 클릭하면 단추가 `OnClick` 이벤트를 생성합니다.  컨트롤의 호스트에 해당 이벤트에 대한 처리기가 있으면 이 처리기가 실행됩니다.|  
|형식 라이브러리|형식 라이브러리는 컨트롤이 지원하는 속성, 메서드 및 이벤트를 컨트롤 컨테이너에 알립니다.  형식 라이브러리는 확장명이 .tlb인 별도의 파일로 유지되거나 컨트롤 내부에 유지됩니다.<br /><br /> 또한 형식 라이브러리에는 컨트롤의 coclass 정보가 있습니다.  coclass는 GUID로 식별되는 COM 클래스로,  컨트롤이 정의하는 하나 이상의 인터페이스가 포함됩니다.<br /><br /> 형식 라이브러리를 보려면 [OLE\/COM 개체 뷰어](../../data/ado-rdo/using-the-ole-com-object-viewer.md)를 사용하십시오.|  
  
 다음 항목에서는 ActiveX 컨트롤 사용에 대해 설명합니다.  
  
-   [Visual C\+\+ 응용 프로그램에 컨트롤 삽입](../../data/ado-rdo/inserting-the-control-into-a-visual-cpp-application.md)  
  
-   [래퍼 클래스](../../data/ado-rdo/wrapper-classes.md)  
  
-   [데이터베이스 연결 만들기](../../data/ado-rdo/creating-database-connections.md)  
  
-   [디자인 타임에 컨트롤 속성 설정](../../data/ado-rdo/setting-control-properties-at-design-time.md)  
  
-   [ActiveX 컨트롤에 이벤트 처리기 설정](../../data/ado-rdo/setting-event-handlers-on-activex-controls.md)  
  
-   [컨트롤의 런타임 동작 수정](../../data/ado-rdo/modifying-a-control-s-run-time-behavior.md)  
  
-   [컨트롤 재배포](../../data/ado-rdo/redistributing-controls.md)  
  
## 참고 항목  
 [데이터 바인딩된 컨트롤\(ADO 및 RDO\)](../../data/ado-rdo/data-bound-controls-ado-and-rdo.md)