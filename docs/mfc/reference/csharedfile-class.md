---
title: "CSharedFile Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSharedFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSharedFile class"
  - "memory files"
  - "shared memory files"
ms.assetid: 5d000422-9ede-4318-a8c9-f7412b674f39
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSharedFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[CMemFile](../../mfc/reference/cmemfile-class.md)\-파생된 클래스를 지 원하는 메모리 파일을 공유 합니다.  
  
## 구문  
  
```  
class CSharedFile : public CMemFile  
```  
  
## 멤버  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CSharedFile::CSharedFile](../Topic/CSharedFile::CSharedFile.md)|`CSharedFile` 개체를 생성합니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CSharedFile::Detach](../Topic/CSharedFile::Detach.md)|공유 메모리 파일을 닫고 해당 메모리 블록의 핸들을 반환 합니다.|  
|[CSharedFile::SetHandle](../Topic/CSharedFile::SetHandle.md)|공유 메모리 파일을 메모리 블록에 첨부합니다.|  
  
## 설명  
 Ram에서이 아닌 디스크에 파일 저장을 제외 하 고 메모리 파일 디스크 파일 처럼 동작 합니다.  메모리 파일 독립 프로세스 간에 개체를 직렬화 하거나 빠른 임시 저장소 또는 원시 바이트를 전송 하기 위한 유용 합니다.  
  
 공유 메모리 파일 사용에 대 한 메모리를 할당 한다는 점에서 다른 메모리 파일에서 다를  [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) Windows 함수.  `CSharedFile` 클래스는 전체적으로 할당 된 메모리 블록에 데이터를 저장 합니다 \(사용 하 여 만든  **GlobalAlloc**\),이 메모리 블록, 클립보드 나 다른 OLE\/COM 단일형 데이터 전송 작업, 예를 들어, DDE를 사용 하 여 사용 하 여 공유 될 수 `IDataObject`.  
  
 **GlobalAlloc** 반환 된 `HGLOBAL` 메모리가 반환 포인터에 대 한 포인터 대신 처리  [malloc](../../c-runtime-library/reference/malloc.md).  `HGLOBAL` 핸들 특정 응용 프로그램에 필요 합니다.  예를 들어, 데이터를 넣으려면 클립보드 필요한는 `HGLOBAL` 처리 합니다.  
  
 참고 `CSharedFile` 하지 사용 메모리 매핑된 파일 및 프로세스 간에 데이터를 직접 공유할 수 없습니다.  
  
 `CSharedFile`개체는 자신의 메모리를 할당할 수 있습니다 자동으로 또는 직접 메모리 블록에 첨부할 수 있는 `CSharedFile` 개체를 호출 하 여  [CSharedFile::SetHandle](../Topic/CSharedFile::SetHandle.md).  두 경우 모두에서 메모리 파일 자동 증가 하는 메모리를 할당 `nGrowBytes`\-크기 만큼 경우 `nGrowBytes` 0이 아닙니다.  
  
 에 대 한 자세한 내용은 문서를 참조 하십시오.  [파일에서 MFC](../../mfc/files-in-mfc.md) 및  [파일 처리](../../c-runtime-library/file-handling.md) 에  *런타임 라이브러리 참조*.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CMemFile](../../mfc/reference/cmemfile-class.md)  
  
 `CSharedFile`  
  
## 요구 사항  
 **헤더:**  afxadv.h  
  
## 참고 항목  
 [CMemFile Class](../../mfc/reference/cmemfile-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)   
 [CMemFile Class](../../mfc/reference/cmemfile-class.md)   
 [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574)   
 [GlobalFree](http://msdn.microsoft.com/library/windows/desktop/aa366579)   
 [GlobalRealloc](http://msdn.microsoft.com/library/windows/desktop/aa366590)