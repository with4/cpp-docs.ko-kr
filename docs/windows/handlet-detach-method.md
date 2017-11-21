---
title: "Handlet:: Detach 메서드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleT::Detach
dev_langs: C++
helpviewer_keywords: Detach method
ms.assetid: f7df0f90-fafb-4d1b-a215-a6c62941f6b0
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0b17d9f720d2fee92cfcf2aaf7b9f452cde32e3e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="handletdetach-method"></a>HandleT::Detach 메서드
현재 HandleT 개체에서 기본 핸들을 분리합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typename HandleTraits::Type Detach();  
```  
  
## <a name="return-value"></a>반환 값  
 기본 핸들입니다.  
  
## <a name="remarks"></a>설명  
 이 작업이 완료 되 면 현재 HandleT가 유효 하지 않은 상태로 설정 됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [HandleT 클래스](../windows/handlet-class.md)