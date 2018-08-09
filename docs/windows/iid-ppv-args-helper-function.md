---
title: IID_PPV_ARGS_Helper 함수 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/IID_PPV_ARGS_Helper
dev_langs:
- C++
helpviewer_keywords:
- IID_PPV_ARGS_Helper function
ms.assetid: afee9b23-8df1-4575-903f-e9ba748418f0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 351e0755f786e69da1dea6a925b7afc7cb6d6bf1
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40011642"
---
# <a name="iidppvargshelper-function"></a>IID_PPV_ARGS_Helper 함수
지정 된 인수의 형식에서 파생 되는 확인 된 `IUnknown` 인터페이스입니다.  
  
> [!IMPORTANT]
>  이 템플릿 특수화 WRL 인프라를 지원 하며 코드에서 직접 사용할 수 없습니다. 사용 하 여 [IID_PPV_ARGS](http://msdn.microsoft.com/library/windows/desktop/ee330727.aspx) 대신 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
template<typename T>  
void** IID_PPV_ARGS_Helper(  
   _Inout_ Microsoft::WRL::Details::ComPtrRef<T> pp  
);  
```  
  
### <a name="parameters"></a>매개 변수  
 *T*  
 인수의 형식은 *pp*합니다.  
  
 *pp*  
 이중 간접 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
 인수 *pp* 에 대 한 포인터-에-a-포인터로 캐스팅 **void**합니다.  
  
## <a name="remarks"></a>설명  
 컴파일 타임 오류가 생성 됩니다 템플릿 매개 변수 *T* 에서 파생 되지 `IUnknown`합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** client.h  
  
## <a name="see-also"></a>참고 항목  
 [참조 (Windows 런타임 라이브러리)](http://msdn.microsoft.com/00000000-0000-0000-0000-000000000000)