---
title: VCPROFILE_ALLOC_SCALE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VCPROFILE_ALLOC_SCALE
dev_langs:
- C++
helpviewer_keywords:
- VCPROFILE_ALLOC_SCALE environment variable
ms.assetid: 5cb5ce27-f9b8-489b-b46c-d6e9bcab2d34
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b7b441f41106544633bd691c409fa04c989146f0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/21/2017
---
# <a name="vcprofileallocscale"></a>VCPROFILE_ALLOC_SCALE
프로필 데이터를 보관에 할당 된 메모리의 양을 수정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
VCPROFILE_ALLOC_SCALE=scale_value  
```  
  
#### <a name="parameters"></a>매개 변수  
 `scale_value`  
 테스트 시나리오를 실행 하기 위한 메모리의 양을 배율 값입니다.  기본값은 1입니다.  
  
## <a name="remarks"></a>설명  
 드문 경우에서 지 원하는 데 사용할 수 있는 충분 한 메모리 되지 테스트 시나리오를 실행 하는 경우 프로필 데이터를 수집 합니다.  이러한 경우에 사용 하 여 메모리 양을 늘릴 수 있습니다 `VCPROFILE_ALLOC_SCALE`합니다.  
  
 메모리가 부족 한지 여부를 나타내는 테스트 실행 도중 오류 메시지를 수신 하는 경우에 더 큰 값을 할당 `VCPROFILE_ALLOC_SCALE`테스트 실행이 메모리 부족 오류 없이 완료 될 때까지, 합니다.  
  
## <a name="example"></a>예  
  
```  
set VCPROFILE_ALLOC_SCALE=2  
```  
  
## <a name="see-also"></a>참고 항목  
 [프로필 기반 최적화 환경 변수](../../build/reference/environment-variables-for-profile-guided-optimizations.md)