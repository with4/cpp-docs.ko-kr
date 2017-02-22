---
title: "CTokenGroups Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CTokenGroups"
  - "ATL.CTokenGroups"
  - "CTokenGroups"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTokenGroups class"
ms.assetid: 2ab08076-4b08-4487-bc70-ec6dee304190
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CTokenGroups Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스에 대 한 래퍼 되는  **TOKEN\_GROUPS** 구조.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
class CTokenGroups  
  
```  
  
## Members  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CTokenGroups::CTokenGroups](../Topic/CTokenGroups::CTokenGroups.md)|생성자입니다.|  
|[CTokenGroups::~CTokenGroups](../Topic/CTokenGroups::~CTokenGroups.md)|소멸자|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CTokenGroups::Add](../Topic/CTokenGroups::Add.md)|추가 된 `CSid` 또는 기존  **TOKEN\_GROUPS** 구조에 `CTokenGroups` 개체.|  
|[CTokenGroups::Delete](../Topic/CTokenGroups::Delete.md)|삭제는 `CSid` 및 이와 관련 된 특성에서의 `CTokenGroups` 개체입니다.|  
|[CTokenGroups::DeleteAll](../Topic/CTokenGroups::DeleteAll.md)|모든 삭제 `CSid` 개체와 연관 된 특성에서의 `CTokenGroups` 개체입니다.|  
|[CTokenGroups::GetCount](../Topic/CTokenGroups::GetCount.md)|개수를 반환 합니다. `CSid` 개체와 연결 된 특성에는  **CTokenGroups**  개체.|  
|[CTokenGroups::GetLength](../Topic/CTokenGroups::GetLength.md)|크기를 반환 하는 `CTokenGroups` 개체입니다.|  
|[CTokenGroups::GetPTOKEN\_GROUPS](../Topic/CTokenGroups::GetPTOKEN_GROUPS.md)|검색에 대 한 포인터는  **TOKEN\_GROUPS** 구조.|  
|[CTokenGroups::GetSidsAndAttributes](../Topic/CTokenGroups::GetSidsAndAttributes.md)|검색은 `CSid` 개체와 특성에 속한는 `CTokenGroups` 개체입니다.|  
|[CTokenGroups::LookupSid](../Topic/CTokenGroups::LookupSid.md)|관련 특성을 검색 한 `CSid` 개체입니다.|  
  
### Public 연산자  
  
|이름|설명|  
|--------|--------|  
|[CTokenGroups::operator const TOKEN\_GROUPS \*](../Topic/CTokenGroups::operator%20const%20TOKEN_GROUPS%20*.md)|캐스트는 `CTokenGroups` 개체에 대 한 포인터는  **TOKEN\_GROUPS** 구조.|  
|[CTokenGroups::operator \=](../Topic/CTokenGroups::operator%20=.md)|할당 연산자입니다.|  
  
## 설명  
 [액세스 토큰](http://msdn.microsoft.com/library/windows/desktop/aa374909) 프로세스 또는 스레드의 보안 컨텍스트를 설명 하 고 Windows NT 또는 Windows 2000 시스템에 로그온 한 각 사용자에 게 할당 되는 개체입니다.  
  
 **CTokenGroups** 클래스에 대 한 래퍼 되는  [TOKEN\_GROUPS](http://msdn.microsoft.com/library/windows/desktop/aa379624) 액세스 토큰의 그룹 보안 식별자 \(Sid\)에 대 한 정보가 포함 된 구조를.  
  
 Windows에서 액세스 제어 모델에 대 한 소개를 참조 하십시오.  [액세스 제어](http://msdn.microsoft.com/library/windows/desktop/aa374860) 에 있는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## 요구 사항  
 **헤더:** atlsecurity.h  
  
## 참고 항목  
 [보안 샘플](../../top/visual-cpp-samples.md)   
 [CSid Class](../../atl/reference/csid-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Security Global Functions](../../atl/reference/security-global-functions.md)