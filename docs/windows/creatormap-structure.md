---
title: "CreatorMap 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreatorMap
- implements/Microsoft::WRL::Details::CreatorMap
dev_langs:
- C++
helpviewer_keywords:
- CreatorMap structure
ms.assetid: 94e40927-90c3-4107-bca3-3ad2dc4beda9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a941f052527b3617772bcb18b2092fdc35ea3a22
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="creatormap-structure"></a>CreatorMap 구조체
Windows 런타임 c + + 템플릿 라이브러리 인프라를 지원 하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
struct CreatorMap;  
```  
  
## <a name="remarks"></a>설명  
 초기화, 등록 및 개체의 등록을 취소 하는 방법에 대 한 정보를 포함 합니다.  
  
 CreatorMap은 다음과 같은 정보가 포함 되어 있습니다.  
  
-   초기화, 등록 및 개체의 등록을 취소 하는 방법.  
  
-   클래식 COM 또는 Windows 런타임 팩터리에 따라 정품 인증 데이터를 비교 하는 방법입니다.  
  
-   인터페이스에 대 한 팩터리 캐시 및 서버 이름에 대 한 정보입니다.  
  
## <a name="members"></a>멤버  
  
### <a name="public-data-members"></a>공용 데이터 멤버  
  
|이름|설명|  
|----------|-----------------|  
|[CreatorMap::activationId 데이터 멤버](../windows/creatormap-activationid-data-member.md)|클래식 COM 클래스 ID 또는 Windows 런타임 이름에 의해 식별 되는 개체 ID를 나타냅니다.|  
|[CreatorMap::factoryCache 데이터 멤버](../windows/creatormap-factorycache-data-member.md)|CreatorMap에 대 한 팩터리 캐시에 대 한 포인터를 저장합니다.|  
|[CreatorMap::factoryCreator 데이터 멤버](../windows/creatormap-factorycreator-data-member.md)|지정 된 CreatorMap에 대 한 팩터리를 만듭니다.|  
|[CreatorMap::serverName 데이터 멤버](../windows/creatormap-servername-data-member.md)|CreatorMap에 대 한 서버 이름을 저장합니다.|  
  
## <a name="inheritance-hierarchy"></a>상속 계층  
 `CreatorMap`  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)