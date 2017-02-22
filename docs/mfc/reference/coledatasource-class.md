---
title: "COleDataSource Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleDataSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "클립보드[C++], MFC 지원"
  - "클립보드[C++], OLE 지원"
  - "COleDataSource class"
  - "data transfer [C++], OLE"
  - "drag and drop [C++], MFC 지원"
  - "IDataObject, MFC encapsulation"
  - "OLE[C++], uniform data transfer"
  - "OLE Clipboard [C++], 지원"
  - "OLE data transfer [C++]"
  - "uniform data transfer"
  - "uniform data transfer, OLE"
ms.assetid: 02c8ee7d-8e10-4463-8613-bb2a0305ca69
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# COleDataSource Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

클립보드 또는 끌어서 놓기 작업 등의 작업을 응용 프로그램 데이터 중 데이터를 제공 합니다 위치에 캐시 역할을 전송 합니다.  
  
## 구문  
  
```  
class COleDataSource : public CCmdTarget  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[COleDataSource::COleDataSource](../Topic/COleDataSource::COleDataSource.md)|`COleDataSource` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleDataSource::CacheData](../Topic/COleDataSource::CacheData.md)|제공 된 데이터를 사용 하 여 지정 된 형식에는  **STGMEDIUM** 구조.|  
|[COleDataSource::CacheGlobalData](../Topic/COleDataSource::CacheGlobalData.md)|제공 된 데이터를 사용 하 여 지정 된 형식에는 `HGLOBAL`.|  
|[COleDataSource::DelayRenderData](../Topic/COleDataSource::DelayRenderData.md)|지연된 렌더링을 사용 하 여 지정 된 형식의 데이터를에서 제공 합니다.|  
|[COleDataSource::DelayRenderFileData](../Topic/COleDataSource::DelayRenderFileData.md)|데이터를 지정 된 형식으로 제공 된 `CFile` 포인터.|  
|[COleDataSource::DelaySetData](../Topic/COleDataSource::DelaySetData.md)|지원 되는 모든 형식에 대 한 호출 `OnSetData`.|  
|[COleDataSource::DoDragDrop](../Topic/COleDataSource::DoDragDrop.md)|데이터 소스를 끌어서 놓기 작업을 수행합니다.|  
|[COleDataSource::Empty](../Topic/COleDataSource::Empty.md)|비웁니다는 `COleDataSource` 데이터 개체입니다.|  
|[COleDataSource::FlushClipboard](../Topic/COleDataSource::FlushClipboard.md)|클립보드에 모든 데이터를 렌더링합니다.|  
|[COleDataSource::GetClipboardOwner](../Topic/COleDataSource::GetClipboardOwner.md)|클립보드에 있는 데이터가 여전히 있는지 확인 합니다.|  
|[COleDataSource::OnRenderData](../Topic/COleDataSource::OnRenderData.md)|지연된 렌더링의 일부로 데이터를 검색합니다.|  
|[COleDataSource::OnRenderFileData](../Topic/COleDataSource::OnRenderFileData.md)|검색 데이터에는 `CFile` 지연된 렌더링의 일부로.|  
|[COleDataSource::OnRenderGlobalData](../Topic/COleDataSource::OnRenderGlobalData.md)|검색 데이터에는 `HGLOBAL` 지연된 렌더링의 일부로.|  
|[COleDataSource::OnSetData](../Topic/COleDataSource::OnSetData.md)|호출 데이터를 대체 하는 `COleDataSource` 개체입니다.|  
|[COleDataSource::SetClipboard](../Topic/COleDataSource::SetClipboard.md)|위치는 `COleDataSource` 클립보드에 있는 개체입니다.|  
  
## 설명  
 OLE 데이터 소스를 직접 만들 수 있습니다.  또는  [활성화](../../mfc/reference/coleclientitem-class.md) 및  [COleServerItem](../../mfc/reference/coleserveritem-class.md) 클래스 만들기 OLE 데이터 원본에 대 한 응답으로 자신의 `CopyToClipboard` 및 `DoDragDrop` 멤버 함수입니다.  참조  [COleServerItem::CopyToClipboard](../Topic/COleServerItem::CopyToClipboard.md) 에 대 한 간략 한 설명입니다.  재정의 `OnGetClipboardData` 추가 클립보드 형식을 OLE 데이터 원본에서 데이터를 추가 하 여 클라이언트 항목 또는 서버 항목 클래스의 멤버 함수에 대해 만들어진는 `CopyToClipboard` 또는 `DoDragDrop` 멤버 함수입니다.  
  
 데이터 전송을 위해 준비 하려고 할 때마다이 클래스의 개체를 만들고 데이터에 가장 적합 한 메서드를 사용 하 여 데이터를 입력 해야 합니다.  여부 데이터 즉시 제공 하는 데이터 소스에 삽입 하는 방법은 직접 영향을 \(즉시 렌더링\) 또는 \(지연 렌더링\) 시.  여는 제공 데이터 사용할 클립보드 형식을 전달 하 여 모든 클립보드 형식에 대 한 \(그리고 옵션인  [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682177) 구조\), 호출  [DelayRenderData](../Topic/COleDataSource::DelayRenderData.md).  
  
 데이터 원본 및 데이터 전송에 대 한 자세한 내용은  [데이터 개체 및 데이터 소스 \(OLE\)](../../mfc/data-objects-and-data-sources-ole.md).  또한 문서  [클립보드 항목](../../mfc/clipboard.md) OLE 클립보드 메커니즘에 설명 합니다.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleDataSource`  
  
## 요구 사항  
 **헤더:**  afxole.h  
  
## 참고 항목  
 [MFC 샘플 HIERSVR](../../top/visual-cpp-samples.md)   
 [MFC OCLIENT 샘플](../../top/visual-cpp-samples.md)   
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleDataObject Class](../../mfc/reference/coledataobject-class.md)