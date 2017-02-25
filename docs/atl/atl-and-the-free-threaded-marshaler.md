---
title: "ATL 및 자유 스레드된 마샬러 | Microsoft Docs"
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
  - "ATL, 자유 스레드된 마샬러"
  - "자유 스레드된 마샬러"
  - "ATL의 FTM"
  - "스레딩[ATL], 자유 스레드된 마샬러"
  - "스레딩[C++], ATL에서 마샬링"
ms.assetid: 2db88a13-2217-4ebc-aa7e-432d5da902eb
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ATL 및 자유 스레드된 마샬러
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL 단순 개체 마법사의 속성 페이지 클래스 \(FTM\) 자유 스레드된 마샬러를 집계 하는 옵션을 제공 합니다.  
  
 마법사 인스턴스를 자유 스레드된 마샬러를 만드는 코드 생성 `FinalConstruct` 해당 인스턴스를 해제 하 고 `FinalRelease`.  A `COM_INTERFACE_ENTRY_AGGREGATE` 매크로 자동으로 해당 COM 맵에 추가 `QueryInterface` 요청에 대 한  [IMarshal](http://msdn.microsoft.com/library/windows/desktop/dd542707) 여 자유 스레드된 마샬러를 처리 합니다.  
  
 자유 스레드된 마샬러 직접 액세스 인터페이스를 개체에 동일한 프로세스에서 스레드의 아파트 간 호출의 속도가 빨라집니다.  이 옵션은 양쪽 스레딩 모델을 사용 하는 클래스를 위한 것입니다.  
  
 이 옵션을 사용할 경우, 클래스 데이터의 스레드 안전성에 대해 책임져야 합니다.  또한 자유 스레드된 마샬러를 집계 하 고 다른 개체에서 얻은 인터페이스 포인터를 사용 해야 하는 개체 인터페이스를 올바르게 마샬링되도록 추가 단계를 수행 해야 합니다.  일반적으로 전역 인터페이스 테이블 \(GIT\)의 인터페이스 포인터를 저장 하 고 사용 될 때마다 GIT에서 포인터를 가져오기 합니다.  ATL 클래스를 제공 합니다.  [CComGITPtr](../atl/reference/ccomgitptr-class.md) 인터페이스 포인터를 GIT에 저장을 사용할 수 있도록 합니다.  
  
## 참고 항목  
 [개념](../atl/active-template-library-atl-concepts.md)   
 [CoCreateFreeThreadedMarshaler](http://msdn.microsoft.com/library/windows/desktop/ms694500)   
 [IMarshal](http://msdn.microsoft.com/library/windows/desktop/dd542707)   
 [When to Use the Global Interface Table](http://msdn.microsoft.com/library/windows/desktop/ms693729)   
 [In\-Process Server Threading Issues](http://msdn.microsoft.com/library/windows/desktop/ms687205)