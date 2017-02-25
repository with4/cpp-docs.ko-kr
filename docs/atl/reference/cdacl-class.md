---
title: "CDacl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CDacl"
  - "CDacl"
  - "ATL.CDacl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDacl class"
ms.assetid: 2dc76616-6362-4967-b6cf-e2d39ca37ddd
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CDacl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스는 DACL \(임의 액세스 제어 목록\) 구조에 대 한 래퍼입니다.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
class CDacl : public CAcl  
  
```  
  
## Members  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CDacl::CDacl](../Topic/CDacl::CDacl.md)|생성자입니다.|  
|[CDacl::~CDacl](../Topic/CDacl::~CDacl.md)|소멸자|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CDacl::AddAllowedAce](../Topic/CDacl::AddAllowedAce.md)|허용 된 ACE \(액세스 제어 항목\)를 추가 하는 `CDacl` 개체입니다.|  
|[CDacl::AddDeniedAce](../Topic/CDacl::AddDeniedAce.md)|추가 하는 거부 ACE는 `CDacl` 개체.|  
|[CDacl::GetAceCount](../Topic/CDacl::GetAceCount.md)|Ace \(액세스 제어 항목\)의 수를 반환 된 `CDacl` 개체입니다.|  
|[CDacl::RemoveAce](../Topic/CDacl::RemoveAce.md)|특정 ACE \(액세스 제어 항목\)를 제거 하는 `CDacl` 개체입니다.|  
|[CDacl::RemoveAllAces](../Topic/CDacl::RemoveAllAces.md)|모든 포함 된 Ace 제거는 `CDacl` 개체입니다.|  
  
### Public 연산자  
  
|이름|설명|  
|--------|--------|  
|[CDacl::operator \=](../Topic/CDacl::operator%20=.md)|할당 연산자입니다.|  
  
## 설명  
 개체의 보안 설명자는 DACL 포함 될 수 있습니다.  DACL에 사용자 및 개체에 액세스할 수 있는 사용자 그룹을 식별 하는 0 개 이상의 Ace를 \(액세스 제어 항목\)이 포함 되어 있습니다.  DACL이 비어 있는 경우 \(즉, 0 Ace 포함\) 액세스가 암시적으로 거부 하므로 액세스가 명시적으로 부여 됩니다.  그러나 개체의 보안 설명자에 DACL이 없으면 개체가 보호 되지 및 모든 완전 한 액세스 권한이.  
  
 개체의 DACL에서 검색 하려면 개체의 소유자 이거나 개체에 대해 액세스 권한이.  개체의 DACL을 변경 하려면 개체에 대 한 WRITE\_DAC 액세스가 있어야 합니다.  
  
 만들기, 추가, 제거 및 삭제에서 Ace를 제공 하는 클래스 메서드 사용을 `CDacl` 개체입니다.  참고  [AtlGetDacl](../Topic/AtlGetDacl.md) 및  [AtlSetDacl](../Topic/AtlSetDacl.md).  
  
 Windows에서 액세스 제어 모델에 대 한 소개를 참조 하십시오.  [액세스 제어](http://msdn.microsoft.com/library/windows/desktop/aa374860) 에 있는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## 상속 계층 구조  
 [CAcl](../../atl/reference/cacl-class.md)  
  
 `CDacl`  
  
## 요구 사항  
 **헤더:** atlsecurity.h  
  
## 참고 항목  
 [보안 샘플](../../top/visual-cpp-samples.md)   
 [CAcl Class](../../atl/reference/cacl-class.md)   
 [ACLs](http://msdn.microsoft.com/library/windows/desktop/aa374872)   
 [ACEs](http://msdn.microsoft.com/library/windows/desktop/aa374868)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Security Global Functions](../../atl/reference/security-global-functions.md)