---
title: 'Eventtargetarray:: Eventtargetarray 생성자 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray::EventTargetArray
dev_langs:
- C++
helpviewer_keywords:
- EventTargetArray, constructor
ms.assetid: 6c6d3737-3cd3-4515-a8f6-d27901bb8ed2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fbfd12ea513044f1062e60f5c73f5089683f043d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
---
# <a name="eventtargetarrayeventtargetarray-constructor"></a>EventTargetArray::EventTargetArray 생성자
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
EventTargetArray(  
   _Out_ HRESULT* hr,  
   size_t items  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `hr`  
 이 생성자 작업을 수행한 후 매개 변수 `hr` 배열의 할당 성공 했는지 아니면 실패 했는지를 나타냅니다. 다음 표에서 가능한 값에 대 한 `hr`합니다.  
  
 S_OK  
 작업에 성공했습니다.  
  
 E_OUTOFMEMORY  
 배열에 대 한 메모리를 할당할 수 없습니다.  
  
 S_FALSE  
 매개 변수 `items` 가 0 보다 작거나 같음.  
  
 `items`  
 할당할 배열 요소의 수입니다.  
  
## <a name="remarks"></a>설명  
 EventTargetArray 클래스의 새 인스턴스를 초기화합니다.  
  
 EventTargetArray는 EventSource 개체에 이벤트 처리기의 배열을 유지 하는 데 사용 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** event.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>참고 항목  
 [EventTargetArray 클래스](../windows/eventtargetarray-class.md)   
 [Microsoft::WRL::Details 네임스페이스](../windows/microsoft-wrl-details-namespace.md)