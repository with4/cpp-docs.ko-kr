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
ms.openlocfilehash: 866159a4b3cbacae8b7ad09154fb93707fe4baac
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39467354"
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
 *spincount*  
 임계 영역 개체의 스핀 수입니다. 기본값은 0입니다.  
  
## <a name="remarks"></a>설명  
 임계 영역 및 스핀 수에 대 한 자세한 내용은 참조는 `InitializeCriticalSectionAndSpinCount` 함수는 **동기화** Windows API 설명서의 섹션입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>참고 항목  
 [CriticalSection 클래스](../windows/criticalsection-class.md)