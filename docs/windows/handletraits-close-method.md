---
title: 'Handletraits:: Close 메서드 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLETraits::Close
dev_langs:
- C++
helpviewer_keywords:
- Close method
ms.assetid: 3c631a7c-ccce-472a-b1da-aab8fa815c13
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1f45f95fb1b060f3892def6dc2962bfffef70c77
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33875616"
---
# <a name="handletraitsclose-method"></a>HANDLETraits::Close 메서드
지정된 된 핸들을 닫습니다.  
  
## <a name="syntax"></a>구문  
  
```  
inline static bool Close(  
   _In_ Type h  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `h`  
 닫기에 대 한 핸들입니다.  
  
## <a name="return-value"></a>반환 값  
 **true 이면** 경우 처리 `h` , 빌드되지 않으면 닫힌 **false**합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>참고 항목  
 [HANDLETraits 구조체](../windows/handletraits-structure.md)