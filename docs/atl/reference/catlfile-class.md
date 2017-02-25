---
title: "CAtlFile Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAtlFile"
  - "ATL::CAtlFile"
  - "ATL.CAtlFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlFile class"
ms.assetid: 93ed160b-af2a-448c-9cbe-e5fa46c199bb
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CAtlFile Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 Windows에 대 한 씬 래퍼 파일 처리 API를 제공 합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
class CAtlFile : public CHandle  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CAtlFile::CAtlFile](../Topic/CAtlFile::CAtlFile.md)|생성자입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAtlFile::Create](../Topic/CAtlFile::Create.md)|파일을 만들거나이 메서드를 호출 합니다.|  
|[CAtlFile::Flush](../Topic/CAtlFile::Flush.md)|파일 버퍼를 지우고 버퍼링 된 모든 데이터를 파일에 기록 될이 메서드를 호출 합니다.|  
|[CAtlFile::GetOverlappedResult](../Topic/CAtlFile::GetOverlappedResult.md)|파일에서 겹쳐진된 작업의 결과 얻으려면이 메서드를 호출 합니다.|  
|[CAtlFile::GetPosition](../Topic/CAtlFile::GetPosition.md)|현재 파일 포인터 위치를 파일에서 가져오려면이 메서드를 호출 합니다.|  
|[CAtlFile::GetSize](../Topic/CAtlFile::GetSize.md)|파일의 바이트 크기를 가져오려면이 메서드를 호출 합니다.|  
|[CAtlFile::LockRange](../Topic/CAtlFile::LockRange.md)|영역에서 다른 프로세스에 액세스 하지 못하도록 파일을 잠그려면이 메서드를 호출 합니다.|  
|[CAtlFile::Read](../Topic/CAtlFile::Read.md)|파일 포인터가 가리키는 위치에 파일에서 데이터를 읽으려면이 메서드를 호출 합니다.|  
|[CAtlFile::Seek](../Topic/CAtlFile::Seek.md)|파일의 파일 포인터를 이동 하려면이 메서드를 호출 합니다.|  
|[CAtlFile::SetSize](../Topic/CAtlFile::SetSize.md)|파일의 크기를 설정 하려면이 메서드를 호출 합니다.|  
|[CAtlFile::UnlockRange](../Topic/CAtlFile::UnlockRange.md)|영역 파일의 잠금을 해제 하려면이 메서드를 호출 합니다.|  
|[CAtlFile::Write](../Topic/CAtlFile::Write.md)|데이터 파일 포인터가 가리키는 위치에 파일을 작성 하려면이 메서드를 호출 합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CAtlFile::m\_pTM](../Topic/CAtlFile::m_pTM.md)|포인터를 `CAtlTransactionManager` 개체|  
  
## 설명  
 파일 처리 요구 비교적 간단 하지만 Windows API를 제공 하는 보다 자세한 추상화 MFC 종속성을 포함 하지 않고 반드시 때이 클래스를 사용 합니다.  
  
## 상속 계층 구조  
 [CHandle](../../atl/reference/chandle-class.md)  
  
 `CAtlFile`  
  
## 요구 사항  
 **헤더:** atlfile.h  
  
## 참고 항목  
 [Marquee 샘플](../../top/visual-cpp-samples.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [CHandle Class](../../atl/reference/chandle-class.md)