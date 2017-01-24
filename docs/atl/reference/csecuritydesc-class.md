---
title: "CSecurityDesc Class | Microsoft Docs"
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
  - "ATL::CSecurityDesc"
  - "ATL.CSecurityDesc"
  - "CSecurityDesc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSecurityDesc class"
ms.assetid: 3767a327-378f-4690-ba40-4d9f6a1f5ee4
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSecurityDesc Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스에 대 한 래퍼 되는  **SECURITY\_DESCRIPTOR** 구조.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
class CSecurityDesc  
  
```  
  
## Members  
  
### Public 생성자  
  
|이름|설명|  
|--------|--------|  
|[CSecurityDesc::CSecurityDesc](../Topic/CSecurityDesc::CSecurityDesc.md)|생성자입니다.|  
|[CSecurityDesc::~CSecurityDesc](../Topic/CSecurityDesc::~CSecurityDesc.md)|소멸자|  
  
### Public 메서드  
  
|이름|설명|  
|--------|--------|  
|[CSecurityDesc::FromString](../Topic/CSecurityDesc::FromString.md)|보안 설명자 문자열 형식에 유효한, 기능적 보안 설명자로 변환합니다.|  
|[CSecurityDesc::GetControl](../Topic/CSecurityDesc::GetControl.md)|정보 보안 설명자에서 검색을 제어합니다.|  
|[CSecurityDesc::GetDacl](../Topic/CSecurityDesc::GetDacl.md)|임의 액세스 제어 목록 \(DACL\) 정보는 보안 설명자를 검색합니다.|  
|[CSecurityDesc::GetGroup](../Topic/CSecurityDesc::GetGroup.md)|주 그룹 정보는 보안 설명자를 검색합니다.|  
|[CSecurityDesc::GetOwner](../Topic/CSecurityDesc::GetOwner.md)|보안 설명자에서 소유자 정보를 검색합니다.|  
|[CSecurityDesc::GetPSECURITY\_DESCRIPTOR](../Topic/CSecurityDesc::GetPSECURITY_DESCRIPTOR.md)|반환에 대 한 포인터는  **SECURITY\_DESCRIPTOR** 구조.|  
|[CSecurityDesc::GetSacl](../Topic/CSecurityDesc::GetSacl.md)|보안 설명자에서 시스템 액세스 제어 목록 \(SACL\) 정보를 검색합니다.|  
|[CSecurityDesc::IsDaclAutoInherited](../Topic/CSecurityDesc::IsDaclAutoInherited.md)|DACL 자동 전파를 지원 하도록 구성 되었는지 확인 합니다.|  
|[CSecurityDesc::IsDaclDefaulted](../Topic/CSecurityDesc::IsDaclDefaulted.md)|보안 설명자는 기본 DACL 구성 되었는지 확인 합니다.|  
|[CSecurityDesc::IsDaclPresent](../Topic/CSecurityDesc::IsDaclPresent.md)|보안 설명자는 DACL이 포함 되어 있는지 확인 합니다.|  
|[CSecurityDesc::IsDaclProtected](../Topic/CSecurityDesc::IsDaclProtected.md)|수정을 방지 하려면 DACL 구성 되었는지 확인 합니다.|  
|[CSecurityDesc::IsGroupDefaulted](../Topic/CSecurityDesc::IsGroupDefaulted.md)|기본적으로 보안 설명자 그룹 보안 식별자 \(SID\) 설정 되었는지 여부를 결정 합니다.|  
|[CSecurityDesc::IsOwnerDefaulted](../Topic/CSecurityDesc::IsOwnerDefaulted.md)|기본적으로 보안 설명자의 소유자 SID 설정 되었는지 여부를 결정 합니다.|  
|[CSecurityDesc::IsSaclAutoInherited](../Topic/CSecurityDesc::IsSaclAutoInherited.md)|SACL 자동 전파를 지원 하도록 구성 되었는지 확인 합니다.|  
|[CSecurityDesc::IsSaclDefaulted](../Topic/CSecurityDesc::IsSaclDefaulted.md)|보안 설명자를 사용 하면 기본 SACL 구성 되었는지 확인 합니다.|  
|[CSecurityDesc::IsSaclPresent](../Topic/CSecurityDesc::IsSaclPresent.md)|보안 설명자를 SACL 포함 되어 있는지 확인 합니다.|  
|[CSecurityDesc::IsSaclProtected](../Topic/CSecurityDesc::IsSaclProtected.md)|SACL 수정을 방지 하도록 구성 되었는지 확인 합니다.|  
|[CSecurityDesc::IsSelfRelative](../Topic/CSecurityDesc::IsSelfRelative.md)|보안 설명자는 자기 상대적 형식을 있는지 확인 합니다.|  
|[CSecurityDesc::MakeAbsolute](../Topic/CSecurityDesc::MakeAbsolute.md)|보안 설명자를 절대 형식으로 변환 하려면이 메서드를 호출 합니다.|  
|[CSecurityDesc::MakeSelfRelative](../Topic/CSecurityDesc::MakeSelfRelative.md)|보안 설명자는 자기 상대적 형식으로 변환 하려면이 메서드를 호출 합니다.|  
|[CSecurityDesc::SetControl](../Topic/CSecurityDesc::SetControl.md)|보안 설명자의 컨트롤 비트를 설정합니다.|  
|[CSecurityDesc::SetDacl](../Topic/CSecurityDesc::SetDacl.md)|DACL에서 정보를 설정합니다.  보안 설명자에서 DACL 이미 있으면 바뀝니다.|  
|[CSecurityDesc::SetGroup](../Topic/CSecurityDesc::SetGroup.md)|주 그룹 정보는 주 그룹 정보를 이미 교체 절대 형식 보안 설명자를 설정 합니다.|  
|[CSecurityDesc::SetOwner](../Topic/CSecurityDesc::SetOwner.md)|모든 소유자 정보를 이미 교체 절대 형식 보안 설명자의 소유자 정보를 설정 합니다.|  
|[CSecurityDesc::SetSacl](../Topic/CSecurityDesc::SetSacl.md)|정보에 SACL을 설정합니다.  보안 설명자에서 SACL 이미 있으면 바뀝니다.|  
|[CSecurityDesc::ToString](../Topic/CSecurityDesc::ToString.md)|보안 설명자를 문자열 형식으로 변환합니다.|  
  
### Public 연산자  
  
|이름|설명|  
|--------|--------|  
|[CSecurityDesc::operator const SECURITY\_DESCRIPTOR \*](../Topic/CSecurityDesc::operator%20const%20SECURITY_DESCRIPTOR%20*.md)|반환에 대 한 포인터는  **SECURITY\_DESCRIPTOR** 구조.|  
|[CSecurityDesc::operator \=](../Topic/CSecurityDesc::operator%20=.md)|할당 연산자입니다.|  
  
## 설명  
 **SECURITY\_DESCRIPTOR** 구조체 개체와 관련 된 보안 정보를 포함 합니다.  응용 프로그램 설정 및 개체의 보안 상태를 쿼리 합니다.이 구조를 사용 합니다.  참고  [AtlGetSecurityDescriptor](../Topic/AtlGetSecurityDescriptor.md).  
  
 응용 프로그램을 수정 해야 하지는  **SECURITY\_DESCRIPTOR** 구조 대신 하 고 직접 제공 하는 클래스 메서드를 사용 해야 합니다.  
  
 Windows에서 액세스 제어 모델에 대 한 소개를 참조 하십시오.  [액세스 제어](http://msdn.microsoft.com/library/windows/desktop/aa374860) 에 있는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## 요구 사항  
 **헤더:** atlsecurity.h  
  
## 참고 항목  
 [보안 샘플](../../top/visual-cpp-samples.md)   
 [SECURITY\_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Security Global Functions](../../atl/reference/security-global-functions.md)