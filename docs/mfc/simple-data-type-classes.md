---
title: "단순 데이터 형식 클래스 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "데이터 클래스[C++]"
  - "스칼라 클래스[C++]"
  - "단순 데이터 형식 클래스"
ms.assetid: 0d591d68-0a33-49e9-8a6d-90c90de5c16a
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 단순 데이터 형식 클래스
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

다음 클래스는 드로잉 좌표, 문자열, 시간 및 날짜 정보, C\+\+ 구문의 편리한 사용의 허용을 캡슐화합니다.  이러한 개체는 광범위하게 매개 변수로서 클래스 라이브러리의 Windows 클래스 멤버 함수에 사용됩니다.  `CPoint`, `CSize`, 및 `CRect`이 **POINT**, **SIZE**, 및 `RECT` 구조체와 각각 일치하기 때문에, [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]에서, 사용자는 어디든지 이러한 C 언어 구조체를 사용할 수 있는 곳이라면 이러한 C\+\+ 클래스 객체를 사용할 수 있습니다.  클래스는 그들의 멤버 함수를 통해 유용한 인터페이스를 제공합니다.  `CStringT`는 매우 유연한 동적 문자열을 제공합니다.  `CTime`, `COleDateTime`, `CTimeSpan`, 및  **COleTimeSpan**은 날짜 및 시간 값을 나타냅니다.  이러한 클래스에 대한 자세한 내용은 [Date and Time](../atl-mfc-shared/date-and-time.md)를 참조하십시오.  
  
 **COle**부터 시작하는 클래스는 OLE에 의해 제공된 데이터 형식의 캡슐화입니다.  이러한 데이터 형식은 다른 OLE 기능의 사용 여부에 관계없이 Windows 프로그램에서 사용될 수 있습니다.  
  
 [CStringT 클래스](../atl-mfc-shared/reference/cstringt-class.md)  
 문자열을 저장합니다.  
  
 [CTime](../atl-mfc-shared/reference/ctime-class.md)  
 절대 날짜 및 시간 값을 저장합니다.  
  
 [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)  
 OLE 자동화 형식 **DATE**을 위한 래퍼  날짜 및 시간 값을 나타냅니다.  
  
 [CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md)  
 상대 날짜 및 시간 값을 저장합니다.  
  
 [COleDateTimeSpan](../atl-mfc-shared/reference/coledatetimespan-class.md)  
 예를 들어 두 `COleDateTime`값의 차이같은, 상대 `COleDateTime` 값을 저장합니다.  
  
 [CPoint](../atl-mfc-shared/reference/cpoint-class.md)  
 \(X, y\) 좌표 쌍을 저장합니다.  
  
 [CSize](../atl-mfc-shared/reference/csize-class.md)  
 거리, 상대 위치, 값 쌍을 저장합니다.  
  
 [CRect](../atl-mfc-shared/reference/crect-class.md)  
 사각형 영역의 좌표를 저장합니다.  
  
 [CImageList](../mfc/reference/cimagelist-class.md)  
 Windows 이미지 목록의 기능을 제공합니다.  이미지 목록은 목록 컨트롤과 트리 컨트롤을 사용하여 사용됩니다.  그들은 또한 같은 크기의 비트맵 집합을 저장하고 보관하기 위해 사용될 수 있습니다.  
  
 [COleVariant](../mfc/reference/colevariant-class.md)  
 OLE 자동화 형식 **VARIANT**을 위한 래퍼  **VARIANT**의 데이터는 여러 형식으로 저장될 수 있습니다.  
  
 [COleCurrency](../mfc/reference/colecurrency-class.md)  
 OLE 자동화 형식 **CURRENCY**의 래퍼, 소수점 앞에 15 자릿수, 뒤 4자릿수를 사용하는 고정 소수점 연산 형식입니다.  
  
> [!NOTE]
>  Visual C\+\+.NET 부터는 `CRect`, `CSize`, 및 `CPoint`는 ATL 또는 MFC 응용 프로그램에서 사용가능해지기 위해 수정됩니다.  더하여, `CString`같은 제공된 MFC 독립적 클래스에 `CStringT`가 덧붙여집니다.  공유된 유틸리티 클래스에 대한 추가 정보는 [Shared Classes](../atl-mfc-shared/atl-mfc-shared-classes.md)를 참조하십시오.  
  
## 참고 항목  
 [클래스 개요](../mfc/class-library-overview.md)