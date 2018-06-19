---
title: CSecurityAttributes 클래스 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes::CSecurityAttributes
- ATLSECURITY/ATL::CSecurityAttributes::Set
dev_langs:
- C++
helpviewer_keywords:
- CSecurityAttributes class
ms.assetid: a094880c-52e1-4a28-97ff-752d5869908e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 03bda174fb85fa6857e22b851b93bcf1b3192716
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32357508"
---
# <a name="csecurityattributes-class"></a>CSecurityAttributes 클래스
이 클래스는 보안 특성 구조에 대 한 씬 래퍼입니다.  
  
> [!IMPORTANT]
>  이 클래스 및 해당 멤버는 Windows 런타임에서 실행 되는 응용 프로그램에서 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```
class CSecurityAttributes : public SECURITY_ATTRIBUTES
```  
  
## <a name="members"></a>멤버  
  
### <a name="public-constructors"></a>Public 생성자  
  
|이름|설명|  
|----------|-----------------|  
|[CSecurityAttributes::CSecurityAttributes](#csecurityattributes)|생성자입니다.|  
  
### <a name="public-methods"></a>Public 메서드  
  
|이름|설명|  
|----------|-----------------|  
|[Csecurityattributes:: Set](#set)|특성을 설정 하려면이 메서드를 호출 하는 `CSecurityAttributes` 개체입니다.|  
  
## <a name="remarks"></a>설명  
 **SECURITY_ATTRIBUTES** 구조에 포함 된 [보안 설명자](http://msdn.microsoft.com/library/windows/desktop/aa379561) 개체 생성에 사용 되며이 구조를 지정 하 여 검색 핸들이 상속 되는지 여부를 지정 합니다.  
  
 Windows에서 액세스 제어 모델에 대 한 소개를 참조 하십시오. [액세스 제어](http://msdn.microsoft.com/library/windows/desktop/aa374860) Windows sdk에서입니다.  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `SECURITY_ATTRIBUTES`  
  
 `CSecurityAttributes`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** atlsecurity.h  
  
##  <a name="csecurityattributes"></a>  CSecurityAttributes::CSecurityAttributes  
 생성자입니다.  
  
```
CSecurityAttributes() throw();
explicit CSecurityAttributes(const CSecurityDesc& rSecurityDescriptor, bool bInheritsHandle = false) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `rSecurityDescriptor`  
 보안 설명자에 대한 참조입니다.  
  
 `bInheritsHandle`  
 새 프로세스가 만들어질 때 반환된 핸들의 상속 여부를 지정합니다. 이 멤버가 true이면 새 프로세스가 핸들을 상속합니다.  
  
##  <a name="set"></a>  Csecurityattributes:: Set  
 특성을 설정 하려면이 메서드를 호출 하는 `CSecurityAttributes` 개체입니다.  
  
```
void Set(const CSecurityDesc& rSecurityDescriptor, bool bInheritHandle = false) throw(...);
```  
  
### <a name="parameters"></a>매개 변수  
 `rSecurityDescriptor`  
 보안 설명자에 대한 참조입니다.  
  
 `bInheritHandle`  
 새 프로세스가 만들어질 때 반환된 핸들의 상속 여부를 지정합니다. 이 멤버가 true이면 새 프로세스가 핸들을 상속합니다.  
  
### <a name="remarks"></a>설명  
 이 메서드는 생성자가 초기화 된 `CSecurityAttributes` 개체입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Security 샘플](../../visual-cpp-samples.md)   
 [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560)   
 [보안 설명자](http://msdn.microsoft.com/library/windows/desktop/aa379561)   
 [클래스 개요](../../atl/atl-class-overview.md)   
 [보안 전역 함수](../../atl/reference/security-global-functions.md)
