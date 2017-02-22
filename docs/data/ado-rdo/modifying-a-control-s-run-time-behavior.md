---
title: "컨트롤의 런타임 동작 수정 | Microsoft Docs"
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
  - "ActiveX 컨트롤[C++], 런타임 동작"
ms.assetid: 78b44b0f-0d5a-4da0-8aa2-595f5789c634
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# 컨트롤의 런타임 동작 수정
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[컨트롤을 삽입](../../data/ado-rdo/inserting-the-control-into-a-visual-cpp-application.md)하고 하나 이상의 [래퍼 클래스](../../data/ado-rdo/wrapper-classes.md)를 생성한 후 컨트롤의 메서드를 호출하고 컨트롤의 이벤트 처리기를 프로그래밍할 수 있습니다.  
  
 컨트롤의 [래퍼 클래스](../../data/ado-rdo/wrapper-classes.md)는 컨트롤의 런타임 동작을 수정하는 데 사용할 수 있는 함수를 지정합니다. 적절한 래퍼 클래스 헤더 파일을 포함하고 메서드를 사용합니다. 속성을 설정하려면 속성 이름 앞에 Set 접두사가 붙은 접근자 메서드를 찾고, 속성을 검색하려면 속성 이름 앞에 Get 접두사가 붙은 접근자 메서드를 찾습니다. 이벤트 처리기는 나중에 작성할 수 있습니다.  
  
 컨트롤은 자동화를 사용하여 구현되므로 전달되는 형식은 BSTR 및 VARIANT 같이 자동화 안전 형식만 될 수 있습니다. 시스템 호출을 사용하여 BSTR 및 VARIANAT를 할당하고 설정할 수 있지만 ALT 래퍼 클래스\([CComBSTR](../../atl/reference/ccombstr-class.md), [CComVariant](../../atl/reference/ccomvariant-class.md)\), Visual C\+\+ COM 컴파일러 지원 래퍼 클래스\([\_bstr\_t](../../cpp/bstr-t-class.md), [\_variant\_t](../../cpp/variant-t-class.md)\) 또는 MFC 래퍼 클래스\([COleVariant](../../mfc/reference/colevariant-class.md)\)를 사용할 수도 있습니다.  
  
 데이터 컨트롤을 추가하는 경우 ActiveX 컨트롤 삽입 마법사는 내부 데이터 개체를 관리하는 데이터 컨트롤의 coclass에 대한 래퍼 클래스를 생성합니다. 이러한 클래스는 일부 RDO나 ADO를 포함하지 않지만 형식 라이브러리에 선언된 내부 개체를 나타냅니다.  
  
 ADO 또는 RDO를 직접 사용하려면 [\#import 지시문](../../preprocessor/preprocessor-directives.md)을 지원하는 [컴파일러 COM 지원 클래스](../../cpp/compiler-com-support-classes.md)나 해당 SDK를 사용하여 ADO 또는 RDO DLL\(Msado15.dll 또는 Msrdo20.dll\)에 직접 연결해야 합니다.  
  
## 런타임에 컨트롤 속성을 설정하려면  
 ActiveX 컨트롤의 일부 속성은 런타임에 읽기 전용이어서 동적 만들기를 어렵게 만들 수 있습니다. 기술 자료 문서 "방법: 런타임에 ActiveX 컨트롤 디자인 타임 속성 설정\(Q260744\)"에 설명된 대로 컨트롤 컨테이너의 [OnAmbientPropertyChange](../Topic/COleControl::OnAmbientPropertyChange.md) 처리기를 재정의하면 속성 초기화를 위해 디자인 모드를 일시적으로 시뮬레이션할 수 있습니다. 기술 자료 문서는 [http:\/\/support.microsoft.com\/](http://support.microsoft.com/)에서 찾을 수 있습니다.  
  
## 참고 항목  
 [ActiveX 컨트롤 사용](../../data/ado-rdo/using-activex-controls.md)