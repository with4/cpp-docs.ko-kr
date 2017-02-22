---
title: "COleStreamFile Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleStreamFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleStreamFile class"
  - "data streams [C++]"
  - "data streams [C++], OLE"
  - "OLE[C++], streams of data"
  - "OLE structured storage [C++]"
  - "streams [C++], OLE"
  - "structured storage in OLE"
ms.assetid: e4f93698-e17c-4a18-a7c0-4b4df8eb4d93
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# COleStreamFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

데이터 스트림을 나타냅니다 \(`IStream`\)에서 복합 파일 OLE 구조적 저장소의 일부로.  
  
## 구문  
  
```  
class COleStreamFile : public CFile  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[COleStreamFile::COleStreamFile](../Topic/COleStreamFile::COleStreamFile.md)|`COleStreamFile` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[COleStreamFile::Attach](../Topic/COleStreamFile::Attach.md)|Stream 개체와 연결합니다.|  
|[COleStreamFile::CreateMemoryStream](../Topic/COleStreamFile::CreateMemoryStream.md)|스트림을 전역 메모리에서 만들어지고 개체와 연결 합니다.|  
|[COleStreamFile::CreateStream](../Topic/COleStreamFile::CreateStream.md)|스트림을 만들고이 개체와 연결 합니다.|  
|[COleStreamFile::Detach](../Topic/COleStreamFile::Detach.md)|스트림 개체에서 분리 합니다.|  
|[COleStreamFile::GetStream](../Topic/COleStreamFile::GetStream.md)|현재 스트림을 반환합니다.|  
|[COleStreamFile::OpenStream](../Topic/COleStreamFile::OpenStream.md)|안전 하 게 스트림을 열고이 개체와 연결 합니다.|  
  
## 설명  
 `IStorage` 개체 스트림을 열 수 또는 아니라면 메모리 스트림을 생성 되기 전에 존재 해야 합니다.  
  
 `COleStreamFile`개체를 정확 하 게 조작  [CFile](../../mfc/reference/cfile-class.md) 개체입니다.  
  
 스트림 및 저장소를 조작 하는 방법에 대 한 자세한 내용은  [컨테이너: 복합 파일](../../mfc/containers-compound-files.md).  
  
 자세한 내용은  [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) 및  [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015) 에 있는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `COleStreamFile`  
  
## 요구 사항  
 **헤더:**  afxole.h  
  
## 참고 항목  
 [CFile Class](../../mfc/reference/cfile-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)