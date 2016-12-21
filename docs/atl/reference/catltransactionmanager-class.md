---
title: "CAtlTransactionManager Class | Microsoft Docs"
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
  - "CAtlTransactionManager"
  - "atltransactionmanager/ATL::CAtlTransactionManager"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlTransactionManager class"
ms.assetid: b01732dc-1d16-4b42-bfac-b137fca2b740
caps.latest.revision: 25
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlTransactionManager Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

CAtlTransactionManager 클래스는 커널 트랜잭션 관리자 \(KTM\) 함수 래퍼를 제공합니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
class CAtlTransactionManager;  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CAtlTransactionManager::~CAtlTransactionManager](../Topic/CAtlTransactionManager::~CAtlTransactionManager.md)|CAtlTransactionManager 소멸자입니다.|  
|[CAtlTransactionManager::CAtlTransactionManager](../Topic/CAtlTransactionManager::CAtlTransactionManager.md)|CAtlTransactionManager 생성자입니다.|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CAtlTransactionManager::Close](../Topic/CAtlTransactionManager::Close.md)|하나는 트랜잭션 핸들을 닫습니다.|  
|[CAtlTransactionManager::Commit](../Topic/CAtlTransactionManager::Commit.md)|트랜잭션을 커밋할 수 요청 합니다.|  
|[CAtlTransactionManager::Create](../Topic/CAtlTransactionManager::Create.md)|트랜잭션 핸들을 만듭니다.|  
|[CAtlTransactionManager::CreateFile](../Topic/CAtlTransactionManager::CreateFile.md)|만들거나 트랜잭션 작업은 디렉터리, 파일 또는 파일 스트림을 엽니다.|  
|[CAtlTransactionManager::DeleteFile](../Topic/CAtlTransactionManager::DeleteFile.md)|트랜잭션 처리 된 작업으로 기존 파일을 삭제합니다.|  
|[CAtlTransactionManager::FindFirstFile](../Topic/CAtlTransactionManager::FindFirstFile.md)|트랜잭션 처리 된 작업으로 파일 또는 하위 디렉터리를 검색합니다.|  
|[CAtlTransactionManager::GetFileAttributes](../Topic/CAtlTransactionManager::GetFileAttributes.md)|트랜잭션 처리 된 작업을 지정한 파일이 나 디렉터리에 대 한 파일 시스템 특성을 검색합니다.|  
|[CAtlTransactionManager::GetFileAttributesEx](../Topic/CAtlTransactionManager::GetFileAttributesEx.md)|트랜잭션 처리 된 작업을 지정한 파일이 나 디렉터리에 대 한 파일 시스템 특성을 검색합니다.|  
|[CAtlTransactionManager::GetHandle](../Topic/CAtlTransactionManager::GetHandle.md)|트랜잭션 핸들을 반환합니다.|  
|[CAtlTransactionManager::IsFallback](../Topic/CAtlTransactionManager::IsFallback.md)|대체 호출을 사용할지 여부를 결정 합니다.|  
|[CAtlTransactionManager::MoveFile](../Topic/CAtlTransactionManager::MoveFile.md)|기존 파일 또는 자식 트랜잭션된 작업을 포함 하는 디렉터리를 이동 합니다.|  
|[CAtlTransactionManager::RegCreateKeyEx](../Topic/CAtlTransactionManager::RegCreateKeyEx.md)|지정 된 레지스트리 키를 만들고 해당 트랜잭션과 연결입니다.  키가 이미 있는 경우이 함수를 엽니다.|  
|[CAtlTransactionManager::RegDeleteKey](../Topic/CAtlTransactionManager::RegDeleteKey.md)|하위 키와 해당 값이 레지스트리에 지정 된 플랫폼에 따라 보기에서 트랜잭션 처리 된 작업을 삭제합니다.|  
|[CAtlTransactionManager::RegOpenKeyEx](../Topic/CAtlTransactionManager::RegOpenKeyEx.md)|지정 된 레지스트리 키를 열고 해당 트랜잭션과 연결.|  
|[CAtlTransactionManager::Rollback](../Topic/CAtlTransactionManager::Rollback.md)|요청 트랜잭션이 롤백됩니다.|  
|[CAtlTransactionManager::SetFileAttributes](../Topic/CAtlTransactionManager::SetFileAttributes.md)|트랜잭션 처리 된 작업으로 파일 또는 디렉터리 특성을 설정합니다.|  
  
### 보호된 데이터 멤버  
  
|Name|설명|  
|----------|--------|  
|[CAtlTransactionManager::m\_bFallback](../Topic/CAtlTransactionManager::m_bFallback.md)|`TRUE`대체를 지 원하는 경우.  `FALSE`그렇지 않으면.|  
|[CAtlTransactionManager::m\_hTransaction](../Topic/CAtlTransactionManager::m_hTransaction.md)|트랜잭션 핸들입니다.|  
  
## 설명  
  
## 상속 계층 구조  
 [ATL::CAtlTransactionManager](../../atl/reference/catltransactionmanager-class.md)  
  
## 요구 사항  
 **헤더:**  atltransactionmanager.h  
  
## 참고 항목  
 [ATL COM Desktop Components](../../atl/atl-com-desktop-components.md)