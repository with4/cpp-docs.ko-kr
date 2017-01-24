---
title: "CAcl Class | Microsoft Docs"
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
  - "CAcl"
  - "ATL::CAcl"
  - "ATLSECURITY/CAcl"
  - "ATL.CAcl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAcl class"
ms.assetid: 20bcb9af-dc1c-4737-b923-3864776680d6
caps.latest.revision: 21
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAcl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스에 대 한 래퍼 되는 `ACL` \(액세스 제어 목록\) 구조가 있습니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
class CAcl  
  
```  
  
## Members  
  
### 공용 Typedefs  
  
|이름|설명|  
|--------|--------|  
|[CAcl::CAccessMaskArray](../Topic/CAcl::CAccessMaskArray.md)|배열을 `ACCESS_MASK`s.|  
|[CAcl::CAceFlagArray](../Topic/CAcl::CAceFlagArray.md)|배열을 `BYTE`s.|  
|[CAcl::CAceTypeArray](../Topic/CAcl::CAceTypeArray.md)|배열을 `BYTE`s.|  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CAcl::CAcl](../Topic/CAcl::CAcl.md)|생성자입니다.|  
|[CAcl::~CAcl](../Topic/CAcl::~CAcl.md)|소멸자|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CAcl::GetAceCount](../Topic/CAcl::GetAceCount.md)|액세스 제어 항목 \(ACE\) 개체를 반환합니다.|  
|[CAcl::GetAclEntries](../Topic/CAcl::GetAclEntries.md)|액세스 제어 목록 \(ACL\) 항목에서 검색 된 `CAcl` 개체입니다.|  
|[CAcl::GetAclEntry](../Topic/CAcl::GetAclEntry.md)|모든 항목에 대 한 정보를 검색 하는 `CAcl` 개체입니다.|  
|[CAcl::GetLength](../Topic/CAcl::GetLength.md)|ACL의 길이 반환 합니다.|  
|[CAcl::GetPACL](../Topic/CAcl::GetPACL.md)|한 팩 \(ACL 포인터\)를 반환합니다.|  
|[CAcl::IsEmpty](../Topic/CAcl::IsEmpty.md)|테스트는 `CAcl` 항목에 대 한 개체.|  
|[CAcl::IsNull](../Topic/CAcl::IsNull.md)|상태를 반환 하는 `CAcl` 개체입니다.|  
|[CAcl::RemoveAce](../Topic/CAcl::RemoveAce.md)|특정 ACE \(액세스 제어 항목\)를 제거 하는 `CAcl` 개체입니다.|  
|[CAcl::RemoveAces](../Topic/CAcl::RemoveAces.md)|모든 Ace \(액세스 제어 항목\)를 제거는 `CAcl` 적용 하는 지정 된 `CSid`.|  
|[CAcl::SetEmpty](../Topic/CAcl::SetEmpty.md)|기호는 `CAcl` 비어 있는 상태로 개체입니다.|  
|[CAcl::SetNull](../Topic/CAcl::SetNull.md)|기호는 `CAcl` 로 개체 `NULL`.|  
  
### Public 연산자  
  
|이름|설명|  
|--------|--------|  
|[CAcl::operator const ACL \*](../Topic/CAcl::operator%20const%20ACL%20*.md)|캐스트는 `CAcl` 개체는 `ACL` 구조.|  
|[CAcl::operator \=](../Topic/CAcl::operator%20=.md)|할당 연산자입니다.|  
  
## 설명  
 **ACL** 구조는 ACL \(액세스 제어 목록\)의 헤더입니다.  ACL 순차 목록 0 개 이상 포함 됩니다.  [Ace](http://msdn.microsoft.com/library/windows/desktop/aa374868) \(액세스 제어 항목\)입니다.  개별 Ace는 acl에서에서 0으로 매겨집니다  *n\-1*여기서  *n* ACL에 Ace입니다.  ACL을 편집 하는 경우 응용 프로그램의 ACL에 액세스 제어 항목 \(ACE\) 인덱스로 참조 합니다.  
  
 두 가지 ACL 형식입니다.  
  
-   임의  
  
-   시스템  
  
 개체의 소유자가 임의의 ACL을 제어 하거나 누구나 부여  **WRITE\_DAC** 개체에 액세스할 수 있습니다.  이 액세스 권한 특정 사용자 및 그룹 개체를 지정 합니다.  예를 들어, 파일의 소유자가 임의의 ACL 사용자 및 그룹 수 및 파일에 액세스할 수 없는 컨트롤에 사용할 수 있습니다.  
  
 개체 수준의 시스템 보안 정보에는 시스템 관리자가 제어 하는 ACL은 시스템의 형태로 관련 있을 수도 있습니다.  시스템 ACL 시스템 관리자 개체에 액세스 하려는 모든 시도 감사할 수 있습니다.  
  
 에 대 한 자세한 내용은  [ACL](http://msdn.microsoft.com/library/windows/desktop/aa374872) 토론에는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Windows에서 액세스 제어 모델에 대 한 소개를 참조 하십시오.  [액세스 제어](http://msdn.microsoft.com/library/windows/desktop/aa374860) 에 있는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## 요구 사항  
 **헤더:** atlsecurity.h  
  
## 참고 항목  
 [Class Overview](../../atl/atl-class-overview.md)   
 [Security Global Functions](../../atl/reference/security-global-functions.md)