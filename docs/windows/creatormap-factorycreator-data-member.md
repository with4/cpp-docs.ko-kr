---
title: 'Creatormap:: Factorycreator 데이터 멤버 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreatorMap::factoryCreator
dev_langs:
- C++
helpviewer_keywords:
- factoryCreator data member
ms.assetid: c9aac363-8f38-4cfd-9605-1e6ac74c5097
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 29a88c34502404de13bd3b93d13c60470e2882ea
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39650718"
---
# <a name="creatormapfactorycreator-data-member"></a>CreatorMap::factoryCreator 데이터 멤버
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT (*factoryCreator)(  
   unsigned int* currentflags,  
   const CreatorMap* entry,  
   REFIID iidClassFactory,  
 IUnknown** factory);  
```  
  
### <a name="parameters"></a>매개 변수  
 *currentflags*  
 중 하나는 [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) 열거자입니다.  
  
 *entry*  
 CreatorMap 합니다.  
  
 *iidClassFactory*  
 인터페이스 ID 클래스 팩터리입니다.  
  
 *팩터리*  
 작업이 완료 되 면 클래스 팩터리의 주소입니다.  
  
## <a name="return-value"></a>반환 값  
 성공하면 S_OK이고, 그렇지 않으면 오류를 나타내는 HRESULT입니다.  
  
## <a name="remarks"></a>설명  
 지정 된 CreatorMap에 대 한 팩터리를 만듭니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** module.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [CreatorMap 구조체](../windows/creatormap-structure.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)