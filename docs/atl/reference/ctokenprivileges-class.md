---
title: "CTokenPrivileges Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CTokenPrivileges"
  - "CTokenPrivileges"
  - "ATL.CTokenPrivileges"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTokenPrivileges class"
ms.assetid: 89590105-f001-4014-870d-142926091231
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTokenPrivileges Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스에 대 한 래퍼 되는  **TOKEN\_PRIVILEGES** 구조.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
class CTokenPrivileges  
  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CTokenPrivileges::CTokenPrivileges](../Topic/CTokenPrivileges::CTokenPrivileges.md)|생성자입니다.|  
|[CTokenPrivileges::~CTokenPrivileges](../Topic/CTokenPrivileges::~CTokenPrivileges.md)|소멸자|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CTokenPrivileges::Add](../Topic/CTokenPrivileges::Add.md)|하나 이상의 권한이 추가 된 `CTokenPrivileges` 개체.|  
|[CTokenPrivileges::Delete](../Topic/CTokenPrivileges::Delete.md)|삭제 권한을에서 `CTokenPrivileges` 개체입니다.|  
|[CTokenPrivileges::DeleteAll](../Topic/CTokenPrivileges::DeleteAll.md)|모든 권한에서 삭제 된 `CTokenPrivileges` 개체입니다.|  
|[CTokenPrivileges::GetCount](../Topic/CTokenPrivileges::GetCount.md)|권한 항목의 개수를 반환 된 `CTokenPrivileges` 개체입니다.|  
|[CTokenPrivileges::GetDisplayNames](../Topic/CTokenPrivileges::GetDisplayNames.md)|검색 표시 이름에 포함 된 권한이 있는 `CTokenPrivileges` 개체입니다.|  
|[CTokenPrivileges::GetLength](../Topic/CTokenPrivileges::GetLength.md)|보유 하는 데 필요한 바이트의 버퍼 크기를 반환의  **TOKEN\_PRIVILEGES** 구조를 표시 하는 `CTokenPrivileges` 개체입니다.|  
|[CTokenPrivileges::GetLuidsAndAttributes](../Topic/CTokenPrivileges::GetLuidsAndAttributes.md)|검색 로컬로 고유 식별자 \(Luid\) 및 특성 플래그는 `CTokenPrivileges` 개체입니다.|  
|[CTokenPrivileges::GetNamesAndAttributes](../Topic/CTokenPrivileges::GetNamesAndAttributes.md)|권한 이름 및 특성 플래그를 검색은 `CTokenPrivileges` 개체입니다.|  
|[CTokenPrivileges::GetPTOKEN\_PRIVILEGES](../Topic/CTokenPrivileges::GetPTOKEN_PRIVILEGES.md)|반환에 대 한 포인터는  **TOKEN\_PRIVILEGES** 구조.|  
|[CTokenPrivileges::LookupPrivilege](../Topic/CTokenPrivileges::LookupPrivilege.md)|지정 된 권한 이름에 연결 된 특성을 검색 합니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CTokenPrivileges::operator const TOKEN\_PRIVILEGES \*](../Topic/CTokenPrivileges::operator%20const%20TOKEN_PRIVILEGES%20*.md)|캐스팅에 대 한 포인터 값을  **TOKEN\_PRIVILEGES** 구조.|  
|[CTokenPrivileges::operator \=](../Topic/CTokenPrivileges::operator%20=.md)|할당 연산자입니다.|  
  
## 설명  
 [액세스 토큰](http://msdn.microsoft.com/library/windows/desktop/aa374909) 프로세스 또는 스레드의 보안 컨텍스트를 설명 하 고 Windows NT 또는 Windows 2000 시스템에 로그온 한 각 사용자에 게 할당 되는 개체입니다.  
  
 액세스 토큰을 사용 하 여 각 사용자에 게 부여 된 다양 한 보안 권한을 설명 합니다.  권한 로컬 고유 식별자 라고 하는 64 비트 숫자의 구성 \([LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261)\)과 문자열 설명자입니다.  
  
 `CTokenPrivileges` 클래스에 대 한 래퍼 되는  [TOKEN\_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630) 구조 및 0 또는 더 많은 권한이 포함 되어 있습니다.  삭제 하거나 제공 된 클래스 메서드를 사용 하 여 쿼리 된 권한은 추가할 수 있습니다.  
  
 Windows에서 액세스 제어 모델에 대 한 소개를 참조 하십시오.  [액세스 제어](http://msdn.microsoft.com/library/windows/desktop/aa374860) 에 있는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## 요구 사항  
 **헤더:** atlsecurity.h  
  
## 참고 항목  
 [보안 샘플](../../top/visual-cpp-samples.md)   
 [TOKEN\_PRIVILEGES](http://msdn.microsoft.com/library/windows/desktop/aa379630)   
 [LUID](http://msdn.microsoft.com/library/windows/desktop/aa379261)   
 [LUID\_AND\_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379263)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Security Global Functions](../../atl/reference/security-global-functions.md)