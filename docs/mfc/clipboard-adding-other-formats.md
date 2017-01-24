---
title: "클립보드: 기타 서식 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "클립보드, 형식"
  - "사용자 지정 클립보드 데이터 형식"
  - "사용자 지정 형식"
  - "사용자 지정 형식, 클립보드에 배치"
  - "서식[C++], 클립보드"
  - "사용자 지정 클립보드 데이터 형식 등록"
ms.assetid: aea58159-65ed-4385-aeaa-3d9d5281903b
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 클립보드: 기타 서식 추가
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

This topic explains how to expand the list of supported formats, particularly for OLE support.  The topic [Clipboard: Copying and Pasting Data](../mfc/clipboard-copying-and-pasting-data.md) describes the minimum implementation necessary to support copying and pasting from the Clipboard.  If this is all you implement, the only formats placed on the Clipboard are `CF_METAFILEPICT`, **CF\_EMBEDSOURCE**, **CF\_OBJECTDESCRIPTOR**, and possibly `CF_LINKSOURCE`.  Most applications will need more formats on the Clipboard than these three.  
  
##  <a name="_core_registering_custom_formats"></a> Registering Custom Formats  
 To create your own custom formats, follow the same procedure you would use when registering any custom Clipboard format: pass the name of the format to the **RegisterClipboardFormat** function and use its return value as the format ID.  
  
##  <a name="_core_placing_formats_on_the_clipboard"></a> Placing Formats on the Clipboard  
 To add more formats to those placed on the Clipboard, you must override the `OnGetClipboardData` function in the class you derived from either `COleClientItem` or `COleServerItem` \(depending on whether the data to be copied is native\).  In this function, you should use the following procedure.  
  
#### To place formats on the Clipboard  
  
1.  `COleDataSource` 개체를 만듭니다.  
  
2.  Pass this data source to a function that adds your native data formats to the list of supported formats by calling `COleDataSource::CacheGlobalData`.  
  
3.  Add standard formats by calling `COleDataSource::CacheGlobalData` for each standard format you want to support.  
  
 This technique is used in the MFC OLE sample program [HIERSVR](../top/visual-cpp-samples.md) \(examine the `OnGetClipboardData` member function of the **CServerItem** class\).  The only difference in this sample is that step three is not implemented because HIERSVR supports no other standard formats.  
  
### 추가 정보  
  
-   [OLE data objects and data sources and uniform data transfer](../mfc/data-objects-and-data-sources-ole.md)  
  
-   [OLE drag and drop](../mfc/drag-and-drop-ole.md)  
  
-   [OLE](../mfc/ole-background.md)  
  
## 참고 항목  
 [클립보드: OLE 클립보드 메커니즘 사용](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)