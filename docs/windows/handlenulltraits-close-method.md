---
title: "Handlenulltraits:: Close 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits::Close
dev_langs: C++
helpviewer_keywords: Close method
ms.assetid: 6fb2fa0d-df20-45dc-856f-f78497f8bdf9
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 45d92fd9d14fa65594db17ce881eb0821810b1dd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="handlenulltraitsclose-method"></a>HANDLENullTraits::Close 메서드
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
 [HANDLENullTraits 구조체](../windows/handlenulltraits-structure.md)