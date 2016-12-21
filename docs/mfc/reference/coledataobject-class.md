---
title: "COleDataObject Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IDataObject"
  - "COleDataObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "클립보드[C++], MFC 지원"
  - "클립보드[C++], OLE 지원"
  - "COleDataObject class"
  - "data transfer [C++]"
  - "data transfer [C++], OLE"
  - "drag and drop [C++], MFC 지원"
  - "IDataObject interface, MFC encapsulation"
  - "OLE[C++], uniform data transfer"
  - "OLE Clipboard [C++], 지원"
  - "OLE data transfer [C++]"
  - "uniform data transfer"
  - "uniform data transfer, OLE"
ms.assetid: d1cc84be-2e1c-4bb3-a8a0-565eb08aaa34
caps.latest.revision: 20
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleDataObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

클립보드에서 끌어서 놓기를 통해 또는 포함 된 OLE 항목에서 다양 한 형식의 데이터를 검색 하기 위한 데이터 전송에 사용 되.  
  
## 구문  
  
```  
class COleDataObject  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[COleDataObject::COleDataObject](../Topic/COleDataObject::COleDataObject.md)|`COleDataObject` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleDataObject::Attach](../Topic/COleDataObject::Attach.md)|지정 된 OLE 데이터 개체에 연결 된 `COleDataObject`.|  
|[COleDataObject::AttachClipboard](../Topic/COleDataObject::AttachClipboard.md)|클립보드에 데이터 개체를 연결 합니다.|  
|[COleDataObject::BeginEnumFormats](../Topic/COleDataObject::BeginEnumFormats.md)|하나 또는 이상의 후속 준비 `GetNextFormat` 호출 합니다.|  
|[COleDataObject::Detach](../Topic/COleDataObject::Detach.md)|연결 된 분리 `IDataObject` 개체입니다.|  
|[COleDataObject::GetData](../Topic/COleDataObject::GetData.md)|연결 된 OLE 데이터 개체를 지정 된 형식에서에서 데이터를 복사 합니다.|  
|[COleDataObject::GetFileData](../Topic/COleDataObject::GetFileData.md)|연결 된 OLE 데이터 개체에 데이터를 복사는 `CFile` 지정 된 형식에 대 한 포인터.|  
|[COleDataObject::GetGlobalData](../Topic/COleDataObject::GetGlobalData.md)|연결 된 OLE 데이터 개체에 데이터를 복사는 `HGLOBAL` 지정 된 형식에서입니다.|  
|[COleDataObject::GetNextFormat](../Topic/COleDataObject::GetNextFormat.md)|다음 데이터 형식을 반환합니다.|  
|[COleDataObject::IsDataAvailable](../Topic/COleDataObject::IsDataAvailable.md)|데이터를 지정 된 형식으로 사용할 수 있는지 여부를 확인 합니다.|  
|[COleDataObject::Release](../Topic/COleDataObject::Release.md)|분리 및 연결 된 해제 `IDataObject` 개체입니다.|  
  
## 설명  
 `COleDataObject`기본 클래스에 없는 것입니다.  
  
 이러한 종류의 데이터 전송 원본과 대상을 포함 합니다.  데이터 원본 개체의 이름으로 구현 되는  [COleDataSource](../../mfc/reference/coledatasource-class.md) 클래스입니다.  때마다 대상 응용 프로그램 데이터를 삭제 하거나 클립보드에서 개체의 붙여넣기 작업을 수행 하 라는 메시지가 표시 되는 `COleDataObject` 클래스를 작성 해야 합니다.  
  
 이 클래스는 데이터를 지정 된 형식으로 있는지 여부를 확인할 수 있습니다.  또한 사용 가능한 데이터 형식 열거 또는 주어진된 형식에 사용할 수 있는지 여부를 확인 하 고 해당 기본 형식에서 데이터를 검색 합니다.  개체 검색을 사용 하는 등 여러 가지 방법으로 수행할 수 있습니다는  [CFile](../../mfc/reference/cfile-class.md), `HGLOBAL`, 또는  **STGMEDIUM** 구조.  
  
 자세한 내용은  [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms683812) 의 구조는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 응용 프로그램에서 데이터 개체를 사용 하는 방법에 대 한 자세한 내용은  [데이터 개체 및 데이터 소스 \(OLE\)](../../mfc/data-objects-and-data-sources-ole.md).  
  
## 상속 계층 구조  
 `COleDataObject`  
  
## 요구 사항  
 **헤더:**  afxole.h  
  
## 참고 항목  
 [MFC 샘플 HIERSVR](../../top/visual-cpp-samples.md)   
 [MFC OCLIENT 샘플](../../top/visual-cpp-samples.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [COleDataSource Class](../../mfc/reference/coledatasource-class.md)   
 [COleClientItem Class](../../mfc/reference/coleclientitem-class.md)   
 [COleServerItem Class](../../mfc/reference/coleserveritem-class.md)   
 [COleDataSource::DoDragDrop](../Topic/COleDataSource::DoDragDrop.md)   
 [CView::OnDrop](../Topic/CView::OnDrop.md)