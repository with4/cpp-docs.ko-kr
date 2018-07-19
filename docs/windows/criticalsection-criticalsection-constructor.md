---
title: 'Criticalsection:: Criticalsection 생성자 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::CriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CriticalSection, constructor
ms.assetid: 930b89be-4d74-46bd-8879-5dd4d15bcbd0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d86c80d169cb6d9794f163290c30bf1b2563588b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33870899"
---
# <a name="criticalsectioncriticalsection-constructor"></a>CriticalSection::CriticalSection 생성자
뮤텍스 개체와 유사하지만 단일 프로세스의 스레드에만 사용할 수 있는 동기화 개체를 초기화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
explicit CriticalSection(  
   ULONG spincount = 0  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `spincount`  
 임계 영역 개체의 스핀 수입니다. 기본값은 0입니다.  
  
## <a name="remarks"></a>설명  
 임계 영역 및 스핀 수에 대 한 자세한 내용은 참조는 **InitializeCriticalSectionAndSpinCount** Windows API 설명서의 동기화 섹션에는 함수입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [CriticalSection 클래스](../windows/criticalsection-class.md)
