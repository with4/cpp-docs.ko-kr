---
title: 'Handlet:: Operator = 연산자 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: 9e42dcca-30fa-4e8b-8954-802fd64a5595
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fa253bec9f150d08f699333cd5d5f6d4538fc2d6
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/08/2018
ms.locfileid: "39653159"
---
# <a name="handletoperator-operator"></a>HandleT::operator= 연산자
지정 된 값을 이동 **HandleT** 개체를 현재 **HandleT** 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HandleT& operator=(  
   _Inout_ HandleT&& h  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 *h*  
 핸들에 rvalue 참조입니다.  
  
## <a name="return-value"></a>반환 값  
 현재에 대 한 참조가 **HandleT** 개체입니다.  
  
## <a name="remarks"></a>설명  
 이 작업을 무효화 합니다 **HandleT** 매개 변수로 지정 된 개체 *h*합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [HandleT 클래스](../windows/handlet-class.md)