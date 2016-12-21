---
title: "CMemFile Class | Microsoft Docs"
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
  - "CMemFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMemFile class"
  - "memory files"
  - "temporary files, memory files"
ms.assetid: 20e86515-e465-4f73-b2ea-e49789d63165
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMemFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[CFile](../../mfc/reference/cfile-class.md)\-메모리 파일을 지 원하는 클래스를 파생 합니다.  
  
## 구문  
  
```  
class CMemFile : public CFile  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CMemFile::CMemFile](../Topic/CMemFile::CMemFile.md)|메모리 파일 개체를 만듭니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMemFile::Attach](../Topic/CMemFile::Attach.md)|연결 블록을 메모리에 `CMemFile`.|  
|[CMemFile::Detach](../Topic/CMemFile::Detach.md)|메모리를 분리 합니다. `CMemFile` 및 분리 된 메모리 블록에 대 한 포인터를 반환 합니다.|  
  
### Protected 메서드  
  
|Name|설명|  
|----------|--------|  
|[CMemFile::Alloc](../Topic/CMemFile::Alloc.md)|메모리 할당 동작을 수정 하려면이 옵션을 재정의 합니다.|  
|[CMemFile::Free](../Topic/CMemFile::Free.md)|메모리 할당 취소 동작을 수정 하려면 다음과 같이 재정의 합니다.|  
|[CMemFile::GrowFile](../Topic/CMemFile::GrowFile.md)|재정의 파일 증가 때 동작을 수정 합니다.|  
|[CMemFile::Memcpy](../Topic/CMemFile::Memcpy.md)|읽고 파일에 쓸 때 메모리 복사 동작을 수정 하려면이 옵션을 재정의 합니다.|  
|[CMemFile::Realloc](../Topic/CMemFile::Realloc.md)|메모리 재할당 동작을 수정 하려면이 옵션을 재정의 합니다.|  
  
## 설명  
 Ram에서이 아닌 디스크에 파일 저장을 제외 하 고 이러한 메모리 파일 디스크 파일 처럼 동작 합니다.  메모리 파일 독립 프로세스 간에 개체를 직렬화 하거나 빠른 임시 저장소 또는 원시 바이트를 전송 하기 위한 유용 합니다.  
  
 `CMemFile`개체는 자신의 메모리를 할당할 수 있습니다 자동으로 또는 직접 메모리 블록에 첨부할 수 있는 `CMemFile` 개체를 호출 하 여  [첨부](../Topic/CMemFile::Attach.md).  두 경우 모두에서 메모리 파일 자동 증가 하는 메모리를 할당 `nGrowBytes`\-크기 만큼 경우 `nGrowBytes` 0이 아닙니다.  
  
 메모리 블록의 소멸 시 자동으로 삭제 됩니다의 `CMemFile` 메모리에서 원래 할당 된 경우 개체는 `CMemFile` 개체입니다. 그렇지 않으면 개체에 연결 된 메모리 할당 해제에 대 한 책임이 있습니다.  
  
 메모리 블록에서 분리할 때 제공 되는 포인터를 통해 액세스할 수 있는 `CMemFile` 개체를 호출 하 여  [분리](../Topic/CMemFile::Detach.md).  
  
 가장 일반적인 사용 `CMemFile` 만드는 것은 `CMemFile` 개체를 호출 하 여 사용 하 고  [CFile](../../mfc/reference/cfile-class.md) 멤버 함수.  참고 해당 만들기는 `CMemFile` 자동으로 열립니다: 호출 하지 않아야  [CFile::Open](../Topic/CFile::Open.md), 디스크 파일에 사용 되는.  때문에 `CMemFile` 디스크 파일에서 데이터 멤버를 사용 하지 않는 `CFile::m_hFile` 사용 되지 않으며 아무 의미가 없습니다.  
  
 `CFile` 멤버 함수  [복제](../Topic/CFile::Duplicate.md),  [LockRange](../Topic/CFile::LockRange.md), 및  [UnlockRange](../Topic/CFile::UnlockRange.md) 에 구현 된 `CMemFile`.  이러한 함수를 호출 하는 경우는 `CMemFile` 개체에 get은  [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 `CMemFile`런타임 라이브러리 함수를 사용 하 여  [malloc](../../c-runtime-library/reference/malloc.md),  [realloc](../../c-runtime-library/reference/realloc.md), 및  [사용 가능한](../../c-runtime-library/reference/free.md) 할당 하 고 할당 취소 할당 메모리. 내장 한  [memcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md) 블록 복사 메모리를 읽고 쓸 때.  이 동작이 나 동작을 변경 하려는 경우 `CMemFile` 파일을 증가 클래스에서 파생 `CMemFile` 및 적절 한 함수를 재정의.  
  
 에 대 한 자세한 내용은 `CMemFile`, 문서를 참고 하십시오  [파일에서 MFC](../../mfc/files-in-mfc.md) 및  [메모리 관리 \(MFC\)](../../mfc/memory-management.md) 표시  [파일 처리](../../c-runtime-library/file-handling.md) 에  *런타임 라이브러리 참조*.  
  
## 상속 계층 구조  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `CMemFile`  
  
## 요구 사항  
 **헤더:**  afx.h  
  
## 참고 항목  
 [CFile Class](../../mfc/reference/cfile-class.md)   
 [계층 구조 차트](../../mfc/hierarchy-chart.md)