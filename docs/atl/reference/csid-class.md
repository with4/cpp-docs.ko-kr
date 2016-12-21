---
title: "CSid Class | Microsoft Docs"
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
  - "CSid"
  - "ATL::CSid"
  - "ATL.CSid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSid class"
ms.assetid: be58b7ca-5958-49c3-a833-ca341aaaf753
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSid Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

이 클래스에 대 한 래퍼 되는 `SID` \(보안 식별자\) 구조.  
  
> [!IMPORTANT]
>  런타임에서 Windows를 실행 하는 응용 프로그램에서이 클래스와 해당 멤버를 사용할 수 없습니다.  
  
## 구문  
  
```  
  
class CSid  
  
```  
  
## Members  
  
### 공용 Typedefs  
  
|Name|설명|  
|----------|--------|  
|[CSid::CSidArray](../Topic/CSid::CSidArray.md)|`CSid` 개체로 이루어진 배열입니다.|  
  
### Public 생성자  
  
|Name|설명|  
|----------|--------|  
|[CSid::CSid](../Topic/CSid::CSid.md)|생성자입니다.|  
|[CSid::~CSid](../Topic/CSid::~CSid.md)|소멸자|  
  
### Public 메서드  
  
|Name|설명|  
|----------|--------|  
|[CSid::AccountName](../Topic/CSid::AccountName.md)|관련 된 계정 이름을 반환의 `CSid` 개체입니다.|  
|[CSid::Domain](../Topic/CSid::Domain.md)|연결 된 도메인 이름을 반환의 `CSid` 개체입니다.|  
|[CSid::EqualPrefix](../Topic/CSid::EqualPrefix.md)|테스트 `SID` \(보안 식별자\) 접두사 같은지.|  
|[CSid::GetLength](../Topic/CSid::GetLength.md)|길이 반환 된 `CSid` 개체입니다.|  
|[CSid::GetPSID](../Topic/CSid::GetPSID.md)|반환에 대 한 포인터는 `SID` 구조.|  
|[CSid::GetPSID\_IDENTIFIER\_AUTHORITY](../Topic/CSid::GetPSID_IDENTIFIER_AUTHORITY.md)|반환에 대 한 포인터는  **SID\_IDENTIFIER\_AUTHORITY** 구조.|  
|[CSid::GetSubAuthority](../Topic/CSid::GetSubAuthority.md)|에 지정한 인증 부분이 반환 된  **SID**  구조.|  
|[CSid::GetSubAuthorityCount](../Topic/CSid::GetSubAuthorityCount.md)|인증 부분이 개수를 반환합니다.|  
|[CSid::IsValid](../Topic/CSid::IsValid.md)|테스트는 `CSid` 개체에 대 한 유효 합니다.|  
|[CSid::LoadAccount](../Topic/CSid::LoadAccount.md)|업데이트는 `CSid` 지정한 계정 이름이 도메인 또는 기존 개체 `SID` 구조.|  
|[CSid::Sid](../Topic/CSid::Sid.md)|ID 문자열을 반환합니다.|  
|[CSid::SidNameUse](../Topic/CSid::SidNameUse.md)|상태에 대 한 설명을 반환 된 `CSid` 개체입니다.|  
  
### 연산자  
  
|||  
|-|-|  
|[연산자 \=](../Topic/CSid::operator%20=.md)|할당 연산자입니다.|  
|[const SID 연산자 \*](../Topic/CSid::operator%20const%20SID%20*.md)|캐스트는 `CSid` 개체에 대 한 포인터는 `SID` 구조.|  
  
### 전역 연산자  
  
|||  
|-|-|  
|[연산자 \= \=](../Topic/CSid::operator%20==.md)|두 보안 설명자 개체가 같은지 여부를 테스트합니다.|  
|[연산자\! \=](../Topic/CSid::operator%20!=.md)|같지 않음에 대해 두 가지 보안 설명자 개체를 테스트합니다.|  
|[연산자 \<](../Topic/CSid::operator%20%3C.md)|두 보안 설명자 개체의 상대 값을 비교합니다.|  
|[연산자 \>](../Topic/CSid::operator%20%3E.md)|두 보안 설명자 개체의 상대 값을 비교합니다.|  
|[연산자 \< \=](../Topic/CSid::operator%20%3C=.md)|두 보안 설명자 개체의 상대 값을 비교합니다.|  
|[연산자 \> \=](../Topic/CSid::operator%20%3E=.md)|두 보안 설명자 개체의 상대 값을 비교합니다.|  
  
## 설명  
 `SID` 구조에 사용자 또는 그룹을 고유 하 게 식별 하는 데 사용 하는 가변 길이 구조체입니다.  
  
 응용 프로그램을 수정 해야 하지는 `SID` 구조는 대신이 래퍼 클래스에서 제공 하는 방법을 사용 합니다.  참고  [AtlGetOwnerSid](../Topic/AtlGetOwnerSid.md),  [AtlSetGroupSid](../Topic/AtlSetGroupSid.md),  [AtlGetGroupSid](../Topic/AtlGetGroupSid.md), 및  [AtlSetOwnerSid](../Topic/AtlSetOwnerSid.md).  
  
 Windows에서 액세스 제어 모델에 대 한 소개를 참조 하십시오.  [액세스 제어](http://msdn.microsoft.com/library/windows/desktop/aa374860) 에 있는 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## 요구 사항  
 **헤더:** atlsecurity.h  
  
## 참고 항목  
 [보안 샘플](../../top/visual-cpp-samples.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Security Global Functions](../../atl/reference/security-global-functions.md)   
 [Operators Alphabetical Reference](../../atl/reference/atl-operators.md)