---
title: CreatorMap 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreatorMap
- implements/Microsoft::WRL::Details::CreatorMap
dev_langs:
- C++
helpviewer_keywords:
- CreatorMap structure
ms.assetid: 94e40927-90c3-4107-bca3-3ad2dc4beda9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 173b41c6d36d36b7d8a0f4e7b024e845eec6ae4a
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39650507"
---
# <a name="creatormap-structure"></a>CreatorMap 구조체
Windows Runtime c + + 템플릿 라이브러리 인프라를 지원 하며 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
struct CreatorMap;  
```  
  
## <a name="remarks"></a>설명  
 초기화, 등록 및 개체의 등록을 취소 하는 방법에 대 한 정보를 포함 합니다.  
  
 **CreatorMap** 다음 정보를 포함 합니다.  
  
-   초기화, 등록 및 개체의 등록을 취소 하는 방법.  
  
-   클래식 COM 또는 Windows 런타임 팩터리에 따라 정품 인증 데이터를 비교 하는 방법입니다.  
  
-   인터페이스에 대 한 팩터리 캐시 및 서버 이름에 대 한 정보입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CreatorMap::activationId 데이터 멤버](../windows/creatormap-activationid-data-member.md)|클래식 COM 클래스 ID 또는 Windows 런타임 이름을 식별 되는 개체 ID를 나타냅니다.|  
|[CreatorMap::factoryCache 데이터 멤버](../windows/creatormap-factorycache-data-member.md)|에 대 한 팩터리 캐시에 대 한 포인터를 저장 합니다 **CreatorMap**합니다.|  
|[CreatorMap::factoryCreator 데이터 멤버](../windows/creatormap-factorycreator-data-member.md)|지정 된 팩터리를 만듭니다 **CreatorMap**합니다.|  
|[CreatorMap::serverName 데이터 멤버](../windows/creatormap-servername-data-member.md)|에 대 한 서버 이름을 저장 합니다 **CreatorMap**합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CreatorMap`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)