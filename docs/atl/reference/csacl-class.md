---
title: "CSacl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CSacl"
  - "ATL::CSacl"
  - "CSacl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSacl class"
ms.assetid: 8624889b-aebc-4183-9d29-a20f07837f05
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CSacl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 SACL \(시스템 액세스 제어 목록\) 구조에 대 한 래퍼입니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
class CSacl : public CAcl  
  
```  
  
## Members  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CSacl::CSacl](../Topic/CSacl::CSacl.md)|생성자입니다.|  
|[CSacl::~CSacl](../Topic/CSacl::~CSacl.md)|소멸자|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CSacl::AddAuditAce](../Topic/CSacl::AddAuditAce.md)|감사 액세스 제어 항목 \(ACE\)을 추가 하는 `CSacl` 개체입니다.|  
|[CSacl::GetAceCount](../Topic/CSacl::GetAceCount.md)|액세스 제어 항목 \(Ace\) 수가 반환 된 `CSacl` 개체.|  
|[CSacl::RemoveAce](../Topic/CSacl::RemoveAce.md)|특정 ACE \(액세스 제어 항목\)를 제거 하는  **CSacl**  개체입니다.|  
|[CSacl::RemoveAllAces](../Topic/CSacl::RemoveAllAces.md)|모든 포함 된 Ace 제거는 `CSacl` 개체입니다.|  
  
### Public 연산자  
  
|Name|설명|  
|----------|--------|  
|[CSacl::operator \=](../Topic/CSacl::operator%20=.md)|할당 연산자입니다.|  
  
## 설명  
 SACL에는 도메인 컨트롤러의 보안 이벤트 로그에 감사 레코드를 생성할 시도 액세스 유형을 지정 하는 액세스 제어 항목을 \(Ace\) 포함 되어 있습니다.  Note SACL 액세스 시도가 발생 한 위치에 도메인 컨트롤러에서 개체의 복제본을 포함 하는 모든 도메인 컨트롤러에 없는 로그 항목을 생성 합니다.  
  
 설정 하거나 검색할 개체의 보안 설명자에서 SACL을 알려진 SE\_SECURITY\_NAME 권한은 요청 하는 스레드의 액세스 토큰에서 활성화 되어야 합니다.  관리자 그룹 기본적으로이 권한이 있으며 다른 사용자 또는 그룹에 부여할 수 있습니다.  권한이 부여 된 것은 아닙니다 반드시 필요한 것: 권한으로 정의 된 작업을 수행 하기 전에 권한을 보안 액세스 토큰에 적용 하려면 사용 해야 합니다.  모델의 특정 시스템 작업에만 사용 하 고 더 이상 필요 없는 경우 다음 사용 권한이 없습니다.  참조  [AtlGetSacl](../Topic/AtlGetSacl.md) 및  [AtlSetSacl](../Topic/AtlSetSacl.md) 알려진 SE\_SECURITY\_NAME 사용의 예입니다.  
  
 사용을 추가, 제거, 작성 및 삭제 Ace에서 제공 하는 클래스 메서드는  **SACL** 개체.  참고  [AtlGetSacl](../Topic/AtlGetSacl.md) 및  [AtlSetSacl](../Topic/AtlSetSacl.md).  
  
 Windows에서 액세스 제어 모델에 대 한 소개를 참조 하십시오.  [액세스 제어](http://msdn.microsoft.com/library/windows/desktop/aa374860) 에 있는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## 상속 계층 구조  
 [CAcl](../../atl/reference/cacl-class.md)  
  
 `CSacl`  
  
## 요구 사항  
 **헤더:** atlsecurity.h  
  
## 참고 항목  
 [CAcl Class](../../atl/reference/cacl-class.md)   
 [ACLs](http://msdn.microsoft.com/library/windows/desktop/aa374872)   
 [ACEs](http://msdn.microsoft.com/library/windows/desktop/aa374868)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Security Global Functions](../../atl/reference/security-global-functions.md)