---
title: 'Synclockt:: | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockT::SyncLockT
dev_langs: C++
helpviewer_keywords: SyncLockT, constructor
ms.assetid: 713dfd9f-7369-4d86-b4a0-8b32c184d89b
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fb7e1f9715f84a272e6bdb1029439f9310a65428
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2017
---
# <a name="synclocktsynclockt-constructor"></a>SyncLockT::SyncLockT 생성자
WRL 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
SyncLockT(  
   _Inout_ SyncLockT&& other  
);  
  
explicit SyncLockT(  
   typename SyncTraits::Type sync = SyncTraits::GetInvalidValue()  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `other`  
 다른 SyncLockT 개체를 rvalue 참조입니다.  
  
 `sync`  
 다른 SyncLockWithStatusT 개체에 대 한 참조입니다.  
  
## <a name="remarks"></a>설명  
 SyncLockT 클래스의 새 인스턴스를 초기화합니다.  
  
 첫 번째 생성자는 매개 변수에서 지정한 다른 SyncLockT 개체에서 현재 SyncLockT 개체 `other`, 되 고 다음 다른 SyncLockT 개체를 무효화 합니다. 두 번째 생성자는 `protected`, 유효 하지 않은 상태로 현재 SyncLockT 개체를 초기화 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>참고 항목  
 [SyncLockT 클래스](../windows/synclockt-class.md)